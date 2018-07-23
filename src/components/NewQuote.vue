<template>
    <section class="new-quote-body">
        <label class="add-label" for="new-quote">Quote</label>
        <textarea name="" v-model="quote" class="form-control" id="new-quote" cols="30" rows="10"></textarea>
        <div class="text-center">
            <button class="btn btn-primary add-btn" @click="createQuote">Add Quote</button>
        </div>
    </section>
</template>

<script>
export default {
        props: {
            addQuote: Function,
        },
        data() {
            return {
                quote: '',
            };
        },
        methods: {
            createQuote() {
                this.addQuote(this.quote);
                this.quote = '';
            },
        },
}
</script>

<style scoped>
    .new-quote-body {
        width: 60%;
    }

    .add-label {
        margin: 0;
    }

    .form-control {
        margin-top: 5px;
        height: 200px;
    }

    .add-btn {
        margin-top: 20px;
    }
</style>

