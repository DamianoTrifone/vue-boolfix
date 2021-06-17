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
      api_url_film: "https://api.themoviedb.org/3/search/movie?", 
      api_url_series: "https://api.themoviedb.org/3/search/tv?",
      api_key: "api_key=61f9977f23d7c1c58e53f8d7ecd5f133", 
      query: "", 
      language: ""
    }
},
   methods: {
    searchItem(string) {
      this.query = string; 
           const film = axios.get(`${this.api_url_film}${this.api_key}&query=${this.query}`)
           const series= axios.get(`${this.api_url_series}${this.api_key}&query=${this.query}`)

          axios.all([film, series])
          .then(
            axios.spread((result1, result2) => {
            this.films = result1.data.results; 
            this.films = result2.data.results;
                  }
          )) 
    },
}
}
</script>

<style lang="scss">
@import "~@fortawesome/fontawesome-free/css/all.min.css";
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>
