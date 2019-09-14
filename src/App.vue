<template>
  <div>
    <h1>Comic Books Characters</h1>
    <div class="main-container">
      <characters-list :characters="characters"></characters-list>
    </div>
  </div>
</template>

<script>
import CharactersList from './components/CharactersList.vue'
export default {
  data(){
    return{
      characters: [],
      selectedCharacter: null,
      favCharacters: []
    }
  },
  components:{

  },
  mounted()
    fetch(https://comicvine.gamespot.com/api/characters/?api_key=708444ed348c988274e7eff457d15885b54be794&format=json)
    .then(res => res.json())
    .then(characters => this.characters = characters)
  }
}
</script>

<style>
</style>