<template>
  <div>
      <div class="container">
          <div class="row">
              <div class="col-12">
                  <h1 class="fw-bold">Film</h1>
              </div>
              <Movies v-for= "movie in movies" :key= "movie.id"  :movie= "movie"/>
          </div>
      </div>

        <div class="container">
          <div class="row">
              <div class="col-12">
                  <h1 class="fw-bold">Serie Tv</h1>
              </div>
              <Movies v-for= "serie in seriesTv" :key= "serie.id"  :movie= "serie"/>
          </div>
      </div>
  </div>
</template>

<script>
import Movies from './Movies.vue';

export default {
    name: 'Main',
    props: {
        'movies': Array,
        'seriesTv': Array
        },
    components: {
        Movies,
    },
    data: function() {
        return {
        
        }
    }
}
</script>

<style>

</style>