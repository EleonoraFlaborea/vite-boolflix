<script >
import SearchForm from './SearchForm.vue'
export default {
    name: 'AppHeader',
    components: {
        SearchForm,
    },
    data: () => ({
        movie: '',
    }),
    methods: {
        updateValue(inputResult) {
            const { name, currentValue } = inputResult;
            this[name] = currentValue;
        },
        sendForm() {
            console.log('dati:', this.movie)
        }
    }
}
</script>

<template>
    <form @submit.pre="sendForm">
        <SearchForm placeholder="Cerca..." name="movie" @value-change="updateValue" />
        <div>
            <button type="button">Cerca</button>
        </div>

        <div class="result">
            <div>{{ this.movie }}</div>
        </div>
    </form>
</template>

<style></style>