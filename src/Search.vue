<template>
  <div class="SearchFormWrap">
    <input 
        class="QueryInput" 
        type="text" 
        placeholder="Search..."
        v-model="Query"
        v-on:keyup.enter="submit"
    >
    <div v-if="submitted == true">
      <h2 class="querySearch">Hasil Pencarian Untuk : {{ Query }} </h2>
        <Cards 
            v-for="content in searchResult" 
            :key="content.title"
            :title="content.htmlTitle"
            :url="content.link"
            :desc="content.snippet"
        />
    </div>
  </div>
</template>

<script>
import Cards from './components/Cards.vue';
export default {
  components: { Cards },
  name: 'SearchForm',
  data() {
    return {
      Query:'',
      searchResult:'',
      submitted: '',
      cseKey: 'xxxxx',
      cseCX: 'xxxxx'
    }
  },
  methods: {
    submit : function () {
      const headers = { "Content-Type": "application/json" };
      fetch(`https://www.googleapis.com/customsearch/v1?key=${ this.cseKey }&cx=${ this.cseCX }&q=${ this.Query }`, {headers})
        .then(response => response.json())
        .then(data => (this.searchResult = data.items))
      this.submitted = true
    }
  }
}
</script>

<style scoped>
  .QueryInput {
    border: 0;
    padding: 0 20px;
    height: 50px;
    width: 800px;
    border-radius: 9px;
    background: #252526;
    color: #fff;
    margin-bottom: 10px;
    margin: 0 auto;
  }
  .querySearch {
      margin: 0 auto;
      width: 700px;
      margin-top: 10px;
      margin-bottom: 10px;
      font-size: 19px;
  }
</style>
