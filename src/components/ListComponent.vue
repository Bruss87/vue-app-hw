<template>
  <li v-on:click="handleClick">{{article.webTitle}}
</template>

<script>
import { eventBus } from '../main.js'
export default {
   name: 'list-component',
   props: ['article'],
   methods: {
       handleClick(){
           eventBus.$emit('selected-article', this.article)
       }
   }
}
</script>

<style>

</style>