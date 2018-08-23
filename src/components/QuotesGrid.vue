<template>
    <div>
    <app-quotes v-for="(quote,index) in quotes" @click.native="deleteQuote(index)">
        {{quote}}
    </app-quotes>
</div>
</template>
<script>
import Quotes from "./Quotes.vue"
    export default{
        props:['quotes'],
        components:{
            appQuotes:Quotes
        },
        methods:{
            deleteQuote:function(index){
                this.$emit('qouteDeleted',index)
            }
        }
    }
</script>