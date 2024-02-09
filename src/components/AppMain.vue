<script >
import { store } from '../data/store.js';

export default {
    name: 'AppMain',
    data: () => ({ store }),
    components: {}
}
</script>

<template>
    <main>
        <section>
            <h1>MOVIES</h1>
            <ul v-for="movie in store.movies" :key="movie.id">
                <li>{{ movie.title }}</li>
                <li>{{ movie.original_title }}</li>
                <li>{{ movie.original_language }}</li>
                <li>{{ movie.vote_average }}</li>
            </ul>
        </section>
        <section>
            <h1>SERIES</h1>
            <ul v-for="serie in store.series" :key="serie.id">
                <li>{{ serie.name }}</li>
                <li>{{ serie.original_name }}</li>
                <li>{{ serie.original_language }}</li>
                <li>{{ serie.vote_average }}</li>
            </ul>
        </section>
    </main>
</template>

<style></style>