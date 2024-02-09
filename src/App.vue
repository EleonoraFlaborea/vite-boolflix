<script>
import axios from 'axios';
import { api } from './data/index.js';
import { store } from './data/store.js';
import SearchForm from './components/SearchForm.vue';


export default {
  name: 'MyApp',
  data: () => ({ store }),
  components: { SearchForm },
  methods: {
    searchMovies(titlefilter) {
      console.log(titlefilter)
    }
  }
}
</script>

<template>
  <SearchForm placeholder="Scrivi..." buttonLabel="Cerca" />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.scss';
</style>
