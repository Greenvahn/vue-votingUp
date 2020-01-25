<template>
  <div id="app">
    <Title msg="Vote the best articles!"></Title>
    <Article v-bind:information="sortedSubmissions"></Article>
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
        submissions: data.articles
      }
    },
  computed: {
    sortedSubmissions () {
      let sortedData = this.submissions;

      sortedData.sort((a, b) => {
        return b.votes - a.votes
      });
      return sortedData;
    }
  }
}
</script>


<style lang="scss">
   @import 'bulma';
</style>