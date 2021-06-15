<template>
  <div id="app">
    <Searchbar @searchedFilm="searchItem"/>

    <div class="film_container">
        <Movies 
        :movie="newFilm" 
        v-for="(film, index) in films" 
        :key="index" 
        :item="film"/>
    </div>
  </div>
</template>

<script>
import Searchbar from './components/Searchbar.vue'
import Movies from './components/Movies.vue'; 
import axios from 'axios'; 


export default {
  name: 'App',
  components: {
    Searchbar,
    Movies  
  },
  data() {
    return {
      newFilm: "", 
      films: [],
      api_url: "https://api.themoviedb.org/3/search/movie?", 
      api_key: "api_key=a31b6f1e88fbabef39333e8fbdcf391b", 
      query: "", 
      language: ""
    }
},
   methods: {
    searchItem(string) {
      this.query = string; 
          axios
          .get(`${this.api_url}${this.api_key}&query=${this.query}`)
          .then(
              (result) => {
                  // console.log(result.data);
                  this.films = result.data.results; 
                  console.log(this.films);
              }
          ) 
    },
}
}
</script>

<style lang="scss">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  .film_container{
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    justify-content: center;

   }
</style>
