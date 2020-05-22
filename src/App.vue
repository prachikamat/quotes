<template>
  <div id="app">
    <!-- Header -->
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <!-- New Quote  -->
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
   <!-- Quote Grid -->
    <app-quote-grid :quotes="quotes"
    @quoteDeleted="deleteQuote"></app-quote-grid>
    <!-- Notice -->
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-success">
          Notice: Click on a Quote to delete it!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';

  export default {
    data: function() {
      return {
        quotes: [
          'Love all, trust a few, do wrong to none'
        ],
        maxQuotes: 12
      };
    },
    methods: {
        newQuote(quote) {
          if(this.quotes.length >= this.maxQuotes) {
              return alert('Please delete quotes first!');
          }
            this.quotes.push(quote);
        },
        deleteQuote(index) {
          this.quotes.splice(index,1);
        }
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote,
      appHeader: Header
    }
  }
</script>

<style>
.row {
  margin: 0;
  padding: 0;
  margin-right: 0 !important;
  margin-left: 0 !important;
}
</style>
