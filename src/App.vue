<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxCount="maxquotes"></app-header>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quotes-grid :quotes="quotes" @qouteDeleted="deleteQuote"></app-quotes-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: Click on Quote to delete it!
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import QuotesGrid from "./components/QuotesGrid.vue"
import NewQuote from "./components/NewQuote.vue"
import Header from "./components/Header.vue"
    export default {
        data:function(){
            return {
                quotes:['What a wonderful world'],
                maxquotes:10
            }
        },
        components:{
            appQuotesGrid:QuotesGrid,
            appNewQuote:NewQuote,
            appHeader:Header
        },
        methods:{
            newQuote:function(quote){
                this.quotes.push(quote)
            },
            deleteQuote:function(index){
                this.quotes.splice(index,1)
            }
        }
    }
</script>

<style>
</style>
