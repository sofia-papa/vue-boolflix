<template>
  <div class="col-3  p-3 mb-3">

      <img class="img-fluid" :src= "imgMovie + movie.poster_path" alt="">
      <h2>{{movie.title ? movie.title : movie.name}}</h2>
      <h2>{{movie.original_title}}</h2>
      <p>{{movie.vote_average}}</p>
      <i class="fas fa-star" v-for= "star in stars(movie.vote_average)" 
      :key= "'stars' + star "></i>
      <i class="far fa-star" v-for= "star in 5 - stars(movie.vote_average)" 
      :key= "'stars' + star "></i>

      <div>
            <img class="img-flag" v-if= "movie.original_language == 'it'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Flag_of_Italy.svg/1200px-Flag_of_Italy.svg.png" alt="">
            <img class="img-flag" v-else-if= "movie.original_language == 'en'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/83/Flag_of_the_United_Kingdom_%283-5%29.svg/1200px-Flag_of_the_United_Kingdom_%283-5%29.svg.png" alt="">
            <p v-else>{{movie.original_language}}</p>
      </div>
  </div>
</template>

<script>
export default {
   name: 'Movies',
   props: ['movie'],
   data: function(){
       return{
           imgMovie: 'https://image.tmdb.org/t/p/w342',
       }
   },
   methods: {
       stars (vote) {
          return Math.ceil(vote/ 2);
       }
   }

}
</script>

<style lang= "scss" scoped>

img.img-flag {
    width: 30px;
}

</style>