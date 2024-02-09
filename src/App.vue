<script>
import { store } from './data/store.js';
import AppHeader from './components/AppHeader.vue';


export default {
  name: 'MyApp',
  data: () => ({ store }),
  components: { AppHeader },
}

</script>

<template>
  <AppHeader />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.scss';
</style>
