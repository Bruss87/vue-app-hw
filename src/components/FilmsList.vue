<template>
  <div>
    <ol>
      <list-component v-for="film in films" :film="film" :key="film.id" ></list-component>
    </ol>
  </div>
</template>

<script>
import ListComponent from './ListComponent.vue'

export default {
  name: 'films-list',
  props: ['films'],
  components:{
    'list-component': ListComponent
  }
}
</script>

<style>

</style>