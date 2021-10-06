<template>
      <form class="d-flex color-bg" v-on:submit.prevent>
          <div class=""> 
                <img src="../assets/boolflix.png" alt="">
          </div>
          <div class="search_bar">
              <input type="text" placeholder="digita il nome del film" v-model.trim= "search"
               @keyup= "$emit('searchInMovies', search)">
               <button class="btn btn-primary" type="submit">Cerca</button>
          </div>
      </form>
  
</template>

<script>

export default {
    name: "Search",
    data: function(){
       return{
           search: "",
       }
    },
}
</script>

<style scoped lang="scss">
@import '../style/variables.scss';

.color-bg{
    background-color: black;
}
input{
    flex-grow: 2;
}

.search_bar{
    margin: 30px 600px;
}

</style>