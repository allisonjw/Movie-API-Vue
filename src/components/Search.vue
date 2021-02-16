<template>
    <div>
        <h1 class="search_instructions">Please Enter a Movie Title</h1>
    <form @submit="searchMovies">
      <input type="text" v-model="search" name="search" placeholder="Movie Title" id="inpt" />
      <input type="submit" value="SEARCH" id="btn" />
    </form>
  </div>
</template>

<script>
export default {
    name: 'Search',
    data() {
    return {
      search: ''
    }
  },
  methods: {
    searchMovies(e) {
      e.preventDefault()
      const newSearch = this.search
      this.$emit('new-search', newSearch)
      this.search = '';
    }
  }
}
</script>

<style scoped>
 #inpt {
    border: 1px solid black;
    padding: 10px;
    width: 300px;
    font-size: 1.2em;
  }
  #btn {
    background-color: purple;
    border: none;
    color: white;
    padding: 10px 20px;
    font-size: 1.2em;
  }
  #btn:hover {
    background-color: indigo;
  }
  .search_instructions {
      color: purple;
      font-size: 3em;
  }
</style>