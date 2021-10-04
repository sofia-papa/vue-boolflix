<template>
      <form class="d-flex" v-on:submit.prevent>
          <div>
                <img src="../assets/boolflix.png" alt="">
          </div>
          <div>
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

input{
    flex-grow: 2;
}

</style>