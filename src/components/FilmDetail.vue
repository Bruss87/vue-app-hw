<template>
<article v-if="film">
      <h1> {{ film.title }} </h1> 
      <button v-on:click="save">Save</button>
      <button v-on:click="remove">Remove</button>
      <h3><span>Director</span>:</h3> {{ film.director }}
      <h3><span>Release Date</span>:</h3>{{ film.release_date }} 
      <h3><span>Rating score</span>:</h3>{{ film.rt_score }} 
      <h3><span>Description</span>:</h3> {{ film.description }} 
      </article>
</template>

<script>
 import { eventBus } from '../main.js'
 export default {
  name: 'film-detail',
  props: ['film'],
  methods: {
      save(){
          eventBus.$emit('saved-film', this.film);
      },
    
      remove() {
           eventBus.$emit("removed-film", this.film);
    }
  }
}
</script>

<style>
article{
    width:400px;
}
button {
  color:black;
  background-color: rgb(12, 122, 85);
  border-radius: 30px;
  font-size: 100%;
  font-family:fantasy;
  padding-bottom: 1px;
  padding-top: 2px;
}

</style>