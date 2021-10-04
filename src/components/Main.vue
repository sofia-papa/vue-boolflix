<template>
  <div>
      <div class="container">
          <div class="row">
              <Movies v-for= "movie in films" :key= "movie.id"  :movie= "movie"/>
          </div>
      </div>
  </div>
</template>

<script>
import Movies from './Movies.vue';

export default {
    name: 'Main',
    props: ['films'],
    components: {
        Movies,
    },
    data: function() {
        return {
            movies: [],
        }
    }
}
</script>

<style>

</style>