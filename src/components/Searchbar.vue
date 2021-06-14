<template>
  <div class="searchbar">
      <div class="ricerca">
        <input type="text">
        <button>Cerca</button>
    </div>
  </div>
</template>

<script>
export default {
    name:"Searchbar"
}
</script>

<style lang="scss">
    .searchbar{
        height: 80px;
        background-color: black;
    }

    .ricerca{
        display: flex;
        justify-content: flex-end;
        align-self: flex-end;
        }

    .ricerca input{
        margin-top: 40px;
        margin-right: 20px;
    }

    .ricerca button{
        margin-top: 40px;
        margin-right: 20px;
    }
</style>