<template>
    <section>
        <h1>Quotes Added</h1>
        <div class="progress">
            <div class="progress-bar" :style="getProgress()">{{quotes}}/{{maxQuotes}}</div>
        </div>
    </section>
</template>

<script>
export default {
    props: {
        maxQuotes: {
            type: Number,
            required: true,
        },
        quotes: {
            type: Number,
            required: true,
        }
    },
    methods: {
        getProgress() {
            return {
                'width': ((this.quotes/this.maxQuotes)*100)+'%',
            };
        },
    },
}
</script>

<style scoped>
    .progress, .progress-bar {
        height: 20px;
    }
</style>
