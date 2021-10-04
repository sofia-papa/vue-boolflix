<template>
  <div class="col-3  p-3 mb-3">
      <h2>{{movie.title ? movie.title : movie.name}}</h2>
      <h2>{{movie.original_title}}</h2>
      <p>{{movie.vote_average}}</p>

      <div>
            <img v-if= "movie.original_language == 'it'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Flag_of_Italy.svg/1200px-Flag_of_Italy.svg.png" alt="">
            <img v-else-if= "movie.original_language == 'en'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/83/Flag_of_the_United_Kingdom_%283-5%29.svg/1200px-Flag_of_the_United_Kingdom_%283-5%29.svg.png" alt="">
            <p v-else>{{movie.original_language}}</p>
      </div>
  </div>
</template>

<script>
export default {
   name: 'Movies',
   props: ['movie']
}
</script>

<style lang= "scss" scoped>
    img{
        width: 30px;
    }

</style>