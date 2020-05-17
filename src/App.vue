<template>
  <div class="container">
    <appHeader :quoteCount="quotes.length" :maxQuotes="maxQuotes" ></appHeader>
    <appNewQuote @quoteAdded="newQuote"></appNewQuote>
    <appQuoteGrid :quotes="quotes" @quoteDeleted="deleteQuote"></appQuoteGrid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on a Quote to delete it!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';

export default {
    data: function() {
        return {
            quotes: ['First Quote'],
            maxQuotes: 10
        }
    },
    methods: {
      newQuote(quote) {
        if( this.quotes.length >= this.maxQuotes) {
          return alert('Please delet Quotes first')
        }
        this.quotes.push(quote);
      },
      deleteQuote(index) {
        this.quotes.splice(index, 1);
      }
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote,
      appHeader: Header
    }
};
</script>

<style lang="scss">
@import "assets/breakpoints";

@media (min-width: $md) {

}
</style>
