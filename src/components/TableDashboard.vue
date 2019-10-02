<template>
<div>
    <header>
      <div class="main-object center">
        <img id="logo" src="@/assets/logo-main.png">
        <h3>STARWARS Version</h3>
      </div>
      <div class="header-flex">
        <p>HARUUL ZANGi CTF 2019</p>
        
        <p>FINAL ROUND</p>
      </div>
    </header>
    <div class="main-table">
      <table>
        <tr>
          <th>Team Name</th>
          <th> Task 1</th>
          <th> Task 2</th>
          <th> Task 3</th>
          <th> Task 4</th>
          <th> Task 5</th>
          <th> Task 6</th>
          <th> Task 7</th>
          <th> Task 8</th>
          <th> Task 9</th>
          <th> Task 10</th>
        <tr>
        <tr>
          <td>Team 1</td>
          <td>1000</td>
          <td>350</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>900</td>
          <td>250</td>
          <td>250</td>

        </tr>
        <tr>
          <td>Team 2</td>
          <td>1000</td>
          <td>350</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>900</td>
          <td>250</td>
          <td>-</td>
          <td>250</td>

        </tr>
        <tr>
          <td>Team 3</td>
          <td>1000</td>
          <td>-</td>
          <td>350</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>900</td>
          <td>250</td>
          <td>250</td>

        </tr>
        <tr>
          <td>Team 4</td>
          <td>1000</td>
          <td>350</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>900</td>
          <td>250</td>
          <td>250</td>

        </tr>
        <tr>
          <td>Team 5</td>
          <td>1000</td>
          <td>350</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>900</td>
          <td>250</td>
          <td>250</td>

        </tr>
        <tr>
          <td>Team 6</td>
          <td>1000</td>
          <td>350</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>900</td>
          <td>250</td>
          <td>250</td>

        </tr>
        <tr>
          <td>Team 7</td>
          <td>1000</td>
          <td>350</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>900</td>
          <td>250</td>
          <td>250</td>

        </tr>
        <tr>
          <td>Team 8</td>
          <td>1000</td>
          <td>350</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>900</td>
          <td>250</td>
          <td>250</td>

        </tr>
        <tr>
          <td>Team 9</td>
          <td>1000</td>
          <td>350</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>900</td>
          <td>250</td>
          <td>250</td>
          
        </tr>
        <tr>
          <td>Team 10</td>
          <td>1000</td>
          <td>350</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>-</td>
          <td>900</td>
          <td>250</td>
          <td>900</td>
        </tr>
      </table>  
    </div>
  </div>
</template>

<script>
export default {
  name: 'TableDashboard',
  props: {
    msg: String
  }
}
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
header{
  margin: 0 3%;
  #logo{
    width: 7%;
  }
  .main-object{
    position: absolute;
    text-align: center;
  }
  .header-flex{
    display: flex;
    justify-content: space-between;
    p{
      font-size: 2vw;
    }
  }
}
.main-table{
  margin: 3% 3%;
  table{
    width: 100%;
    border-collapse:separate; 
    border-spacing: 0 2.5em;
    tr{
    }
    td{
      text-align: center;
      // color: #EED100;
      font-size: 1rem;
    }
  }
}
</style>>
