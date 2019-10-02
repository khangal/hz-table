<template>
  <div id="app">
    <TableDashboard/>
  </div>
</template>

<script>
import TableDashboard from "./components/TableDashboard.vue";
import axios from "axios";
import "@/assets/stylesheet.scss";
import "@/assets/Font/starwars.css";


export default {
  name: "app",
  components: {
    TableDashboard
  },
  mounted() {
    // setInterval(() => {
    //   axios.get("http://localhost:8000/api/v1/scoreboard", {}).then(res => {
    //     console.log("----------------------------");
    //     console.log(res.data.data);
    //     console.log("----------------------------");
    //   });
    // }, 1000)
  }
};
</script>

<style>
#app {

  font-family: "STARWARS";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #fff;
  margin-top: 2%;
}
</style>
