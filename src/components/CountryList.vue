<template>
  <ul>
      <country-list-item
        v-for="(country, index) in countries"
        :key='index'
        :country='country'>
      </country-list-item>
  </ul>
</template>

<script>
import CountryListItem from './CountryListItem';

export default {
    name: 'country-list',
    props: ['countries'],
    components: {'country-list-item': CountryListItem},
}
</script>

<style>

</style>