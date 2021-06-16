<template>
<main>
  <div class="film">
      <li>
        <img class="copertina" :src="'https://image.tmdb.org/t/p/w342/' + item.poster_path" alt="../assets/foto_assente.jpg">
        <h2>{{ item.name }}</h2>
        <h3>Titolo originale: {{ item.original_name }}</h3>
        <h3>Lingua originale: {{ item.original_language }} <img class="bandiera" src="../assets/it.png" alt="Bandiera Italiana" v-if="item.original_language == 'it'"><img class="bandiera" src="../assets/en.png" alt="Bandiera Inglese" v-if="item.original_language == 'en'"></h3>
        <h4>Voto degli utenti: <i v-for="i in 5" :key="i">{{ item.vote_average }}</i></h4>  
      </li>
    </div>
</main>    
</template>

<script>
export default {
    name:"movies",
    props: ["item"],

    // created: {
    //   raiting: Math.floor(item.vote_average)
    // }

}
</script>

<style lang="scss">
    main{
        width: 80%;
        margin: 0 auto;
    }
    .bandiera{
        width: 25px;
    }
    .copertina{
        width: 342px;
        padding: 15px;
    }
    .film{
        // display: flex;
        // flex-wrap: wrap;
        // justify-content: center;
        float: left;
        width: 500px;
        padding: 20px 20px;
    }

    .film h2,
    h3,
    h4 {
        padding-left: 15px;
    }

    li{
        width: 50%;
        padding: 40px;
        list-style: none;
    }
</style>