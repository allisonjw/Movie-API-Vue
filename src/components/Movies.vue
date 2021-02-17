<template>
  <div class="movie_holder">
    <section class="section" v-for="movie in movies" :key="movie.imdbID">
        <h2>{{movie.Title}}</h2>
        <h2>Year: <span>{{movie.Year}}</span></h2>
        <h2>IMDB ID: <span>{{movie.imdbID}}</span></h2>
        <img :src="movie.Poster" >
    </section> 
  </div> 
</template>
<script>

  export default {
    name: 'Movies',
    props: ['movies'],
  }
</script>

<style>
  .movie_holder {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .section {
    align-items: center;
    background-color: #000000c2;;
    display: flex;
    flex-direction: column;
    margin: 2% 12%;
    border-radius: 1%;
    width: 45%;
  }
  h2 {
      color: white;
  }
  img {
      width: 50%;
      margin: 2%;
  }
  .plot {
      width: 50%;
  }
</style>