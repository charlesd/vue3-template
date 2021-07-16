<template>
  <div id="app">
    <table>
      <thead>
        <tr>
          <th>Country</th>
          <th>Population</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="{ id, name, population } in countries" :key="id">
          <td>{{ name }}</td>
          <td>{{ population }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
//import HelloWorld from "./components/HelloWorld";
export default {
  name: "App",
  components: {
    //    HelloWorld,
  },
  data() {
    return {
      countries: [],
    };
  },
  created() {
    fetch(`https://restcountries.eu/rest/v2/regionalbloc/nafta`)
      .then((res) => res.json())
      .then((json) => (this.countries = json));
  },
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
