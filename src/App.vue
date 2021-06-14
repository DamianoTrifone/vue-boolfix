<template>
  <div id="app">
    <Searchbar @searchedFilm="searchItem"/>
  </div>
</template>

<script>
import Searchbar from './components/Searchbar.vue'

export default {
  name: 'App',
  components: {
    Searchbar
   
  }
}
</script>

<style lang="scss">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>
