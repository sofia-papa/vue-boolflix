<template>
  <div id="app">
    <Search @searchInMovies= "searchInMovies" />
    <Main :movies= "films"/>
  </div>
</template>

<script>
import Search from './components/Search.vue';
import Main from './components/Main.vue';
import axios from "axios";

export default {
  name: 'App',
  components: {
   Search,
   Main
  },
   data: function(){
    return{
      apiUrl: "https://api.themoviedb.org/3/search/movie",
      apiKey: "3640ad97ed2ac5bae387b7477da6d53f",
      films: [],
    }
   },

  methods: {
    searchInMovies: function (searching){
      axios.get(this.apiUrl, {
        params: {
          api_key : this.apiKey,
          query : searching,
          language: 'it-IT'
        },
      }).then(
        (risposta) => {
          this.films = [...risposta.data.results];
          console.log(this.films);
        }).catch(
          (errore) =>{
            console.warn("errore", errore);
          }
      )
    }
    
  },
}
  
   
</script>

<style lang="scss">
@import './style/variables.scss';

  
</style>
