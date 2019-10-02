<template>
  <div id="app">
    <table>
      <tr>
        <td></td>
      </tr>
    </table>
  </div>
</template>

<script>
import TableDashboard from "./components/TableDashboard.vue";
import axios from "axios";

export default {
  name: "app",
  components: {
    TableDashboard
  },
  mounted() {
    setInterval(() => {
      axios.get("http://localhost:8000/api/v1/scoreboard", {}).then(res => {
        console.log("----------------------------");
        console.log(res.data.data);
        console.log("----------------------------");
      });
    }, 1000)
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
