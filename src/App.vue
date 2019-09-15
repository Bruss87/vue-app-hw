<template>
  <div>
    <h1>Guardian Articles List</h1>
    <div class="main-container">
      <articles-list :articles="articles"></articles-list>
    </div>
  </div>
</template>

<script>
import ArticlesList from './components/ArticlesList.vue'
export default {
  data(){
    return{
      articles: [],
      selectedArticle: null,
      savedArticles: []
    }
  },
  components:{
     "articles-list": ArticlesList
  },
  mounted(){
  fetch('https://content.guardianapis.com/search?api-key=test&page-size=25')
    .then(res => res.json())
    .then(articles => this.articles = articles)
  }
  }
</script>

<style>
</style>