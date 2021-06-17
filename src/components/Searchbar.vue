<template>
    <div class="searchbar">
        <div class="ricerca">
            <img src="https://fontmeme.com/permalink/210615/5f7112a65daf3df48c305aae945b6fbd.png" alt="">
            <input type="text" placeholder="Ricerca il film o la serie"  
            v-model.trim="usersearch"
            @keyup="$emit('searchedFilm', usersearch)">
            <button>Cerca</button>
            </div>
    </div>
</template>

<script>
export default {
    name:"searchbar",
    data(){
        return{
            usersearch: ''
        }
    }
   
}
</script>

<style lang="scss">
    .searchbar{
        height: 80px;
        background-color: black;
        position: relative
    }

    .ricerca{
        display: flex;
        justify-content: flex-end;
        align-self: flex-end;
    }

    .ricerca img{
        display: flex;
        justify-content: flex-start;
        position: absolute;
        left: 10px;
        top: 8px;
    }
    .ricerca input{
        margin-top: 40px;
        margin-right: 20px;
    }

    .ricerca button{
        margin-top: 40px;
        margin-right: 20px;
        padding: 2px 8px;
    }
</style>