<template>
  <div>
    <ol>
      <list-component v-for="(article, index) in articles" :article="article" :key="index"></list-component>
    </ol>
  </div>
</template>

<script>
import ListComponent from './ListComponent.vue'
export default {
  name: 'articles-list',
  props: [articles],
  components:{
    'list-component': ListComponent
  }
}
</script>

<style>

</style>