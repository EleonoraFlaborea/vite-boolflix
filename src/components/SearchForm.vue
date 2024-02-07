<script >
export default {
    name: 'SearchForm',
    data: () => ({
        currentValue: '',
    }),
    props: {
        name: 'movie',
        placeholder: String
    },
    emits: ['value-change']
};
</script>

<template>
    <section class="form-section container pt-5">
        <div>
            <input type="text" :placeholder="placeholder" v-model.trim="currentValue"
                @keyup="$emit('value-change', { name, currentValue })">
        </div>
    </section>
</template>

<style></style>