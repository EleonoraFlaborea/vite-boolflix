<script>
import axios from 'axios';
const endpoint = 'https://api.themoviedb.org/3/search/movie?api_key=5b239fcf9ce7a251e2b2063ceef54e47&query=witch';
import { store } from './data/store.js';


import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';



export default {
  name: 'MyApp',
  components: {
    AppHeader,
    AppMain,
  },
  created() {
    axios.get(endpoint).then(res => {
      store.products = res.data.results;
      console.log(res.data.results);
    })
  }
}

</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.scss';
</style>
