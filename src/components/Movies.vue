<template>
<main>
  <div class="film">
      <li>
        <img v-if="item.poster_path != null" class="copertina" :src="'https://image.tmdb.org/t/p/w342/' + item.poster_path">
        <img class="copertina" v-else src="../assets/foto_assente.jpg">
        <h2>{{ item.name }}</h2>
        <h3>Titolo originale: {{ item.original_name }}</h3>
        <h3>Lingua originale: {{ item.original_language }} <img class="bandiera" src="../assets/it.png" alt="Bandiera Italiana" v-if="item.original_language == 'it'"><img class="bandiera" src="../assets/en.png" alt="Bandiera Inglese" v-if="item.original_language == 'en'"></h3>
        <h4>Voto degli utenti:</h4>  
        <div>
            <i 
            v-for="n in vote()"
            :key="`full-${n}`"
            class="fas fa-star"
            ></i>
            <i
            v-for="n in (5 - vote())"
            :key="`empty-${n}`"
            class="far fa-star"></i>
        </div>
      </li>
    </div>
</main>    
</template>

<script>
export default {
    name:"movies",
    props: ["item"],

     methods: {
      vote() {
            return Math.ceil(this.item.vote_average/2);
        }
    }

}
</script>

<style lang="scss">
    main{
        width: 100%;
        margin: 0 auto;
    }
    .bandiera{
        width: 25px;
    }
    .copertina{
        width: 342px;
        height: 420px;
        padding: 15px;
    }
    .film{
        float: left;
        width: 500px;
        padding: 20px 20px;
    }

    .film h2,
    h3,
    h4 {
        padding-left: 15px;
        max-height: 100px;
     }

    li{
        width: 50%;
        padding: 40px;
        list-style: none;
    }

    i{
        font-size: 15px;
        margin-left: 13px;
        margin-top: 8px;
        color: yellow;
    }
</style>