<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>

        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <!-- 載入 component QuoteGrid ，並把 quotes 傳進去  -->
        <app-quote-grid :quotes="quotes" @quoteDeleted="doDeleteQuote"></app-quote-grid>

        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to Delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid';
    import NewQuote from './components/NewQuote';
    import Header from './components/Header';

    export default {
        data: function() {
            return {
                quotes: [ // 存使用者輸入的 quote 內容
                    'Just a Quote to see something.'
                ],
                maxQuotes: 10 // 最多可以輸入10個
            }
        },
        components: {
            'app-quote-grid': QuoteGrid, // 也可以寫成 appQuoteGrid vue 會自動對應
            'app-new-quote': NewQuote,
            'app-header': Header
        },
        methods: {
            newQuote: function(quote) { // 也可以寫成 newQuote(quote) {...} 
                if (this.quotes.length >= this.maxQuotes) {
                    alert('Please delete Quotes first!');
                    return;
                }
                this.quotes.push(quote);
            },
            doDeleteQuote: function(index) {
                this.quotes.splice(index, 1); // splice: 從 array 中第index筆移除1筆資料
            }
        }
    }
</script>

<style>
</style>
