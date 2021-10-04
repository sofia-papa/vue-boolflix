<template>
  <div>
      <div class="container">
          <div class="row">
              <Movies v-for= "movie in movies" :key= "movie.id"  :movie= "movie"/>
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