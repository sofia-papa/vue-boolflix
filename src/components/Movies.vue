<template>
  <div>
      <h1>{{movie.title}}</h1>
      <h2>{{movie.original_title}}</h2>
      <h2>{{movie.original_language}}</h2>
      <p>{{movie.vote_avarage}}</p>
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