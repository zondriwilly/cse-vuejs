<template>
  <div id="app">
    <div class="siteIdentity">
      <h1 class="siteTitle">Codeturnal CSE</h1>
    </div>
    <Search/>
  </div>
</template>

<script>
  import Search from './Search.vue'
  export default {
    name: 'CustomSearchEngine',
    components: {
      Search
    },
  }
</script>

<style>
  *, *::before, *::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  body {
    font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
    background: #1e1e1e;
    color: #fff;
  }
  #app {
    width: 800px;
    margin: 0 auto;
  }
  .siteTitle {
    margin: 30px 0;
    margin-top: 25vh;
    margin-bottom: 10px;
  }
</style>