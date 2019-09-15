<template>
  <div>
      <ul>
          <h2> Saved Films </h2>
          <li v-for="film in savedFilms" :film="savedFilms" :key="film.id">{{ film.title }} </li>
     </ul>
      </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
name: 'saved-films',
props: ['savedFilms']
}
</script>

<style lang="css" scoped>
ul {
  list-style: none;
  border: 1px solid navy;
  width: 200px;
  height: auto;
  padding: 10px;
  padding-top:0px;
  margin-top: 0px;
  margin-right:20px;
  font-weight: normal;
  border-radius: 10px;
  background-color: rgb(12, 122, 85);
}
li {
  padding:5px;
}
</style>>
