<template>
    <div class="row">
        <!-- 為了取得要被刪除的 quote，必須於 v-for 加上每個 quote 所在的 index -->
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote';

    export default {
        props: { // 也可以寫成 props: [quotes]
            quotes: {
                type: Array
            }
        },
        components: {
            'app-quote': Quote // 也可以寫成 appQuote vue 會自動對應
        },
        methods: {
            deleteQuote: function(index) {
                // 向 parent component告知要刪除的 index
                this.$emit('quoteDeleted', index);
            }   
        }
    }
</script>

<style>
</style>
