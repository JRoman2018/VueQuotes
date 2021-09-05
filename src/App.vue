<template>
  <div class="container">
    <quote-grid :quotes="quotes"></quote-grid>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
export default {
  components: { QuoteGrid },
  data() {
    return { quotes: ['Just a Quote to see something.'], maxQuotes: 10 };
  },
};
</script>

<style></style>
