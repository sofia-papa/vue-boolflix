<template>
  <div id="app">
    <SearchBar />
  </div>
</template>

<script>
import SearchBar from './components/Searchbar.vue'

export default {
  name: 'App',
  components: {
   SearchBar,
  }
}
</script>

<style lang="scss">
@import './style/variables.scss';

  
</style>
