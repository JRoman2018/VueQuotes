<template>
  <div class="row">
    <app-quote v-for="quote in quotes" :key="quote">
      <p>{{ quote }}</p>
    </app-quote>
  </div>
</template>

<script>
import Quote from './Quote.vue';
export default {
  components: { AppQuote: Quote },
  props: ['quotes'],
};
</script>

<style scoped></style>
