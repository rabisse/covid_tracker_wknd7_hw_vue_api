<template>
    <li @click='handleClick'>{{country.All.country}}</li>
</template>

<script>
import {eventBus} from '@/main.js';

export default {
    name: 'country-list-item',
    props: ['country'],
    methods: {
        handleClick() {
            eventBus.$emit('selected-country', this.country)
        },
    },
}
</script>

<style>

</style>