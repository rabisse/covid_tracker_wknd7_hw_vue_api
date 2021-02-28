<template>
  <main id="app">
    <h1>World Covid Tracker</h1>
    <h3>Select a country below to see details</h3>
    <section id='content'>
      <country-list :countries="countries"></country-list>
      <country-details v-if='selectedCountry' :country='selectedCountry'></country-details>
    </section>
  </main>
</template>

<script>
import CountryList from '@/components/CountryList';
import CountryDetails from '@/components/CountryDetails';
import {eventBus} from './main.js';

export default {
  name: 'App',
  data() {
    return {
      countries: [],
      selectedCountry: null,
    }
  },
  mounted() {
    this.getCountries(),

    eventBus.$on('selected-country', (country) => {
      this.selectedCountry = country
    })
  },

  methods: {
    getCountries: function() {
      fetch('https://covid-api.mmediagroup.fr/v1/cases')
      .then(res => res.json())
      .then(data => this.countries = data)
    },
  },
  components: {
    'country-list': CountryList,
    'country-details': CountryDetails
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


#content {
  display: grid;
  grid-template-columns: 2fr 3fr;
  height: 100%;
  grid-gap: 1em;
}

</style>
