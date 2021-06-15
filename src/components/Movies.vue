<template>
  <div class="film">
        <img :src="item.poster_path" alt="">
        <h2>{{ item.title }}</h2>
        <h3>Titolo originale: {{ item.original_title }}</h3>
        <h3>Lingua originale: {{ item.original_language }} <img src="../assets/it.png" alt="Bandiera Italiana" v-if="item.original_language == 'it'"><img src="../assets/en.png" alt="Bandiera Inglese" v-if="item.original_language == 'en'"></h3>
        <h4>Voto degli utenti: {{ item.vote_average }}</h4>  
    </div>
</template>

<script>
export default {
    name:"movies",
    props: ["item"]
}
</script>

<style>
    
</style>