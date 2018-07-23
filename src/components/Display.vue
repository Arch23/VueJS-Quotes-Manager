<template>
    <section class="d-flex flex-wrap display-quotes">
        <app-quote v-for="(quote,index) in quotes" :key="index" :quote="quote" :index="index"></app-quote>
    </section>
</template>

<script>
    import Quote from './Quote.vue';
    export default {
        props: {
            quotes: {
                type: Array,
                required: true,
            }
        },
        components: {
            'app-quote': Quote,
        },
    }
</script>

<style scoped>
</style>

