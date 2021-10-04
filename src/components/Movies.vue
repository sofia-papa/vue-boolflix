<template>
  <div class="col-3  p-3 mb-3">
      <h1>{{movie.title}}</h1>
      <h2>{{movie.original_title}}</h2>
      <h2>{{movie.original_language}}</h2>
  </div>
</template>

<script>
export default {
   name: 'Movies',
   props: ['movie']
}
</script>

<style>

</style>