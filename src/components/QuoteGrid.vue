<template>
  <div class="row">
    <app-quote
      v-for="(quote, index) in quotes"
      :key="quote"
      @click.native="deleteQuote(index)"
    >
      {{ quote }}
    </app-quote>
  </div>
</template>

<script>
import Quote from './Quote.vue';
export default {
  components: { AppQuote: Quote },
  props: ['quotes'],
  methods: {
    deleteQuote(index) {
      this.$emit('quoteDeleted', index);
    },
  },
};
</script>

<style scoped></style>
