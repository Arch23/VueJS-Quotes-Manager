<template>
    <div class="border rounded quote" @click="deleteQuote">
        <p>{{quote}}</p>
    </div>
</template>

<script>
    import {eventBus} from '../main';
    export default {
        props: {
            quote: {
                type: String,
                required: true,
            },
            index: {
                type: Number,
                required: true,
            }
        },
        methods: {
            deleteQuote() {
                eventBus.$emit('deleteQuote',{index: this.index});
            },
        }
}
</script>

<style scoped>
    .quote {
        font-family: Arizonia;
        font-size: 2.5em;
        padding: 25px;
        margin: 0 20px 10px 0;
        max-width: 200px;
    }
</style>

