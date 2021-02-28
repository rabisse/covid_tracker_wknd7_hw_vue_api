<template>
  <article>
      <h2>{{country.All.country}}</h2>
      <p>Confirmed Cases: {{country.All.confirmed}}</p>
      <p>Recovered: {{country.All.recovered}}</p>
      <p>Deaths Reported: {{country.All.deaths}}</p>
  </article>
</template>

<script>
export default {
    name: 'country-detail',
    props: ['country'],
}
</script>

<style>

</style>