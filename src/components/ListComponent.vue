<template>
  <li v-on:click="handleClick">{{film.title}}</li>
</template>

<script>
import { eventBus } from '../main.js'
export default {
   name: 'list-component',
   props: ['film'],
   methods: {
       handleClick(){
           eventBus.$emit('selected-film', this.film)
       }
   }
}
</script>

<style>

</style>