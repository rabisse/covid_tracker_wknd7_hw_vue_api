<template>
  <div id="app">
    <h1>World Covid Tracker</h1>
    <section>
      <!-- <countries-list ></countries-list> -->
    </section>

  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      countries: [],
      selectedCountry: null,
    }
  },
  mounted() {
    this.getCountries()
  },
  methods: {
    getCountries: function() {
      fetch('https://covid-api.mmediagroup.fr/v1/cases')
      .then(res => res.json())
      .then(data => this.countries = data)
    },
  },
  components: {

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
