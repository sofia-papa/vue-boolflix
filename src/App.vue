<template>
  <div id="app">
    <Search @searchInMovies= "searchInMovies" />
    <Main :movies= "films" :seriesTv= "seriesTv"/>
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
      apiMovieUrl: "https://api.themoviedb.org/3/search/movie",
      apiSerieUrl: "https://api.themoviedb.org/3/search/tv",
      apiKey: "3640ad97ed2ac5bae387b7477da6d53f",
      films: [],
      seriesTv: [],
    }
   },

  methods: {
    searchInMovies: function (searching){
      axios.get(this.apiMovieUrl, {
        params: {
          api_key : this.apiKey,
          query : searching,
          language: 'it-IT'
        },
      }).then(
        (risposta) => {
          this.films = [...risposta.data.results];
          console.log(this.films);
        })
        .catch(
          (errore) =>{
            console.warn("errore", errore);
          })

      axios.get(this.apiSerieUrl, {
        params: {
          api_key : this.apiKey,
          query : searching,
          language: 'it-IT'
        },
      }).then(
        (risposta) => {
          this.seriesTv = [...risposta.data.results];
          console.log(this.seriesTv);
        })
        .catch(
          (errore) =>{
            console.warn("errore", errore);
          },
      )
    }
  }
}
  
   
</script>

<style lang="scss">
@import './style/variables.scss';

  
</style>
