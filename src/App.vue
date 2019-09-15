<template>
  <div>
    <h1>Studio Ghibli Films List</h1>
    <div class="main-container">
      <div><films-list :films="films"></films-list></div>
      <div><film-detail :film="selectedFilm"></film-detail></div>
      <div><saved-films :savedFilms="savedFilms"></saved-films></div>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js'
import FilmsList from './components/FilmsList.vue'
import FilmDetail from './components/FilmDetail.vue'
import SavedFilms from './components/SavedFilms.vue'


export default {
  data(){
    return{
      films: [],
      selectedFilm: null,
      savedFilms: []
    }
  },
  components:{
     "films-list": FilmsList,
     "film-detail": FilmDetail,
     "saved-films": SavedFilms
  },
  mounted(){
  fetch('https://ghibliapi.herokuapp.com/films?items=50')
    .then(res => res.json())
    .then(films => this.films = films)

    eventBus.$on('selected-film', film => this.selectedFilm = film)

    eventBus.$on('saved-film', savedFilm => this.savedFilms.push(savedFilm))

    eventBus.$on("removed-film", film => this.savedFilms.splice(film.id, 1))
  }
}
</script>

  <style lang="css" scoped>
    .main-container {
      display: flex;
      flex-flow: row;
      justify-content: space-between;
      font-family:fantasy;
    }
    
  </style>