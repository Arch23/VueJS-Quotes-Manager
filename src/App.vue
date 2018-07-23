<template>
    <div class="container">
        <app-header :maxQuotes="MAX_QUOTES" :quotes="quotes.length"></app-header>
        <app-new-quote :addQuote="addQuote"></app-new-quote>
        <app-display :quotes="quotes"></app-display>
        <div class="alert alert-info" role="alert">Info: Click on a Quote to delete it</div>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import NewQuote from './components/NewQuote.vue';
    import Display from './components/Display.vue';
    import {eventBus} from './main';
    export default {
        data() {
            return {
                MAX_QUOTES: 10,
                quotes: [],
            };
        },
        components: {
            'app-header': Header,
            'app-new-quote': NewQuote,
            'app-display': Display,
        },
        methods: {
            addQuote(quote) {
                quote = quote.trim();
                if(quote && quote.length>0){
                    if(this.quotes.length < 10){
                        this.quotes.push(quote);
                    }else{
                        alert('Reached max number of quotes, delete some.');
                    }
                }
            },
        },
        created() {
            eventBus.$on('deleteQuote',(data)=>{
                this.quotes.splice(data.index,1);
            });
        },
    };
</script>

<style>
    section {
        margin: 50px auto 0 auto;
    }
</style>
