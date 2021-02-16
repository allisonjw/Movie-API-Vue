<template>
  <div>
    <section class="section">
        <h2>{{movies.Title}}</h2>
          <h2>Rating: <span>{{movies.Rated}}</span></h2>
          <h2>Year: <span>{{movies.Year}}</span></h2>
          <h2>Actors: <span>{{movies.Actors}}</span></h2>
          <h2 class="plot">{{movies.Plot}}</h2>
          <img :src="movies.Poster" >
    </section> 
  </div> 
</template>
<script>

  export default {
    name: 'Movies',
    props : ['movies']
  }
</script>

<style>
  .section {
    align-items: center;
    background-color: #000000c2;;
    display: flex;
    flex-direction: column;
    margin: 2% 12%;
    border-radius: 1%;
  }
  h2 {
      color: white;
  }
  img {
      width: 30%;
      margin: 2%;
  }
  .plot {
      width: 50%;
  }
</style>