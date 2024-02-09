<script>
import axios from 'axios';
import { api } from '../data/index.js';
import { store } from '../data/store.js';
import SearchForm from '../components/SearchForm.vue';

export default {
    name: 'MyApp',
    data: () => ({ store }),
    components: { SearchForm },
    methods: {
        setTitleFilter(term) {
            store.filter = term;
        },

        searchMovies() {
            if (!store.filter) {
                store.movies = [];
                return;
            }
            const { baseUri, apiKey, language } = api;

            axios.get(`${baseUri}/search/movie?api_key=${apiKey}&language=${language}&query=${store.filter}`)
                .then(res => {
                    store.movies = res.data.results;
                    console.log(res.data.results);
                })
                .catch((err) => {
                    console.log(err)
                })
        }
    }
}
</script>

<template>
    <SearchForm placeholder="Scrivi..." buttonLabel="Cerca" @form-submit="searchMovies" @term-change="setTitleFilter" />
</template>

<style lang="scss" scoped></style>
