<template>
  <div id="app">
    <Search v-on:new-search="searchMovies" />
    <Movies :movies="movies"/>
  </div>
</template>

<script>
import Movies from './components/Movies.vue';
import Search from './components/Search.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Movies,
    Search
  }, 
  data() {
      return {
        movies: null,
        search: 'Splash'
      };
    },
  methods: {
    searchMovies(newSearch) {
      this.search = newSearch
      const url = `http://www.omdbapi.com/?t=${newSearch}&plot=full&apikey=2550f986`
      axios
        .get(url)
        .then(res => {
          this.movies = res.data;
        })
    },
    fetchMovie(search) {
      const url = `http://www.omdbapi.com/?t=${search}&plot=full&apikey=2550f986`
      axios
        .get(url)
        .then(res => {
          this.movies = res.data;
          console.log('checking api call', res.data)
        })
    },
  },
  mounted() {
    this.fetchMovie(this.search)
   }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
