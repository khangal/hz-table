<template>
  <div>
    <header>
      <div class="main-object center">
        <img id="logo" src="@/assets/logo-main.png" />
        <h3>STARWARS <br class="br" />VERSION</h3>
      </div>
      <div class="header-flex">
        <p>HARUUL ZANGi CTF 2019</p>

        <p>FINAL ROUND</p>
      </div>
    </header>
    <div class="main-table">
      <table>
        <thead>
          <tr>
            <th>Pos</th>
            <th>Team Name</th>
	<th v-for="c in challenges" :key="`${c.name}1`">{{ c.name }}</th>
            <th>Score</th>
          </tr>
        </thead>
        <transition-group
          name="team-list"
          tag="tbody"
          class="scoreboard"
          style="z-index:10000"
        >
          <tr v-for="t in sortedTeams" :key="t.id">
            <td>{{ t.pos }} .</td>
            <td>
              <img class="team-heads" :class="changePosition(t.id)" :src="require(`@/assets/heads/` + t.id +`.png`)">
              {{ t.name }}</td>
            <td v-for="c in challenges" :key="c.id">
              {{ getSolve(c.id, t.id) }}
            </td>
            <td>{{ t.score }}</td>
          </tr>
        </transition-group>
      </table>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { BASE_URL } from "@/constants";

const formatTeams = apiResponse => {
  return apiResponse.data.data.map(item => {
    return {
      id: item.id,
      name: item.name,
      score: 0,
      pos: item.pos || 10
    };
  });
};

const formatChallenges = apiResponse => {
  return apiResponse.data.data;
};

export default {
  name: "TableDashboard",
  data() {
    return {
      teams: [],
      challenges: [],
      solves: []
    };
  },
  props: {
    msg: String
  },

  async mounted() {
    this.teams = formatTeams(await axios.get(`${BASE_URL}/api/v1/teams`));
    this.challenges = formatChallenges(
      await axios.get(`${BASE_URL}/api/v1/challenges`)
    );

    setInterval(async () => {
      let promises = [];

      this.teams.forEach(team => {
        promises.push(axios.get(`${BASE_URL}/api/v1/teams/${team.id}/solves`));
      });

      const [resp1, resp2] = await Promise.all([
        Promise.all(promises),
        axios.get(`${BASE_URL}/api/v1/scoreboard`)
      ]);

      const solvesByTeams = resp1.map(item => item.data && item.data.data);
      const scoreboard = resp2.data.data;

      scoreboard.forEach(item => {
        let team = this.teams.find(team => team.name === item.name);
        team.score = item.score;
        team.pos = item.pos;
      });

      let allSolves = [];

      solvesByTeams.forEach((solves) => {
        allSolves = [...allSolves, ...solves];
      });

      this.solves = allSolves;
    }, 1000);
  },

  methods: {
    getSolve(challengeId, teamId) {
      const solution = this.solves.find(
        solve => solve.challenge_id === challengeId && solve.team === teamId
      );

      if (solution) {
        return "✔";
      } else {
        return "✘";
      }
    },
    changePosition(id){
      if(id === 7){
        return 'margin-head'
      }
      else if(id === 3){
        return 'margin-head'
      }
      else if(id === 2){
        return 'margin-head'
      }
       else if(id === 39){
        return 'margin-head'
      }
       else if(id === 38){
        return 'margin-head'
      }
       else if(id === 27){
        return 'margin-head'
      }
       else if(id === 37){
        return 'margin-head'
      }
      else if(id === 36){
        return 'margin-head'
      }
      else if(id === 155){
        return 'margin-head'
      }
    }
  },

  computed: {
    sortedTeams() {
      return this.teams.concat().sort((a, b) => a.pos - b.pos);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
header {
  margin: 0 3%;
  #logo {
    width: 7%;
  }
  .br {
    margin-top: 5px;
  }
  .main-object {
    position: absolute;
    text-align: center;
    top : 2%;
  }
  .header-flex {
    display: flex;
    justify-content: space-between;
    p {
      font-size: 2vw;
    }
  }
}
header .br{
    margin-top: 5px;
}
.main-table {
  margin-top: 3%;
  table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0 2.5em;
    table-layout: fixed;
    tr {
    }
    td {
      text-align: center;
      // color: #EED100;
      font-size: 1rem;
      position: relative;
    }
  }
}
.team-heads{
  width: 30px;
  // margin-top: -40px;
  left: -36px;
  position: absolute;
}
.team-list-move {
  /* applied to the element when moving */
  transition: transform 0.5s cubic-bezier(0.55, 0, 0.1, 1);
  transition: transform 1s;
}
.margin-head{
  margin-top: -10px;
}
</style>
