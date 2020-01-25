<template>
  <div id="app">
    <Title msg="Vote the best articles!"></Title>
    <Article></Article>
  </div>
</template>

<script>
import Title from './components/Title.vue'
import Article from './components/Article.vue'
import {data} from './js/data.js'

export default {
  name: 'app',
  components: {
    Title,
    Article
  },
  data(){
    return{
      stateData: data.articles
    }
  }
}
</script>


<style lang="scss">
   @import 'bulma';
</style>