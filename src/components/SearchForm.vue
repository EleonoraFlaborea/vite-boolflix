<script >
export default {
    name: 'SearchForm',
    data: () => ({ term: '' }),
    props: {
        buttonLabel: String,
        placeholder: String,
    },
    emits: ['form-submit', 'term-change'],
};

</script>

<template>
    <form @submit.prevent="$emit('form-submit')">
        <input type="text" :placeholder="placeholder" v-model.trim="term" @keyup="$emit('term-change', term)">
        <button>{{ buttonLabel }} </button>
    </form>
</template>

<style></style>