<template>
  <div class="film">
      <ul>
        <img :src="'https://image.tmdb.org/t/p/w342/' + item.poster_path" alt="../assets/foto_assente.jpg">
        <h2>{{ item.title }}</h2>
        <h3>Titolo originale: {{ item.original_title }}</h3>
        <h3>Lingua originale: {{ item.original_language }} <img class="bandiera" src="../assets/it.png" alt="Bandiera Italiana" v-if="item.original_language == 'it'"><img class="bandiera" src="../assets/en.png" alt="Bandiera Inglese" v-if="item.original_language == 'en'"></h3>
        <h4>Voto degli utenti: <i v-for="i in 5" :key="i"></i>{{ item.vote_average }}</h4>  
      </ul>
    </div>
</template>

<script>
export default {
    name:"movies",
    props: ["item"]
}
</script>

<style>
    .bandiera{
        width: 15px;
    }
    .film img{
        width: 342px;
    }
    .film{
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
</style>