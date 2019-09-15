<template>
  <div>
    <h1>Studio Ghibli Films List</h1>
    <div class="main-container">
      <films-list :films="films"></films-list>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js'
import FilmsList from './components/FilmsList.vue'
export default {
  data(){
    return{
      films: [],
      selectedFilm: null,
      savedFilms: []
    }
  },
  components:{
     "films-list": FilmsList
  },
  mounted(){
  fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films)
  }
  }
</script>

<style>
</style>