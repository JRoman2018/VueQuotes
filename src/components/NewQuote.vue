<template>
  <div class="row">
    <form>
      <div
        class="
          col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3
          form-group
        "
      >
        <label for="quote"></label>
        <textarea
          id="quote"
          class="form-control"
          rows="3"
          placeholder="Write a quote..."
          v-model="quote"
        ></textarea>
      </div>

      <div
        class="
          col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3
          form-group
        "
      >
        <div class="alert alert-danger text-center" v-if="!!error">
          {{ error }}
        </div>
        <button class="btn btn-primary" @click.prevent="createNew">
          Add Quote
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: '',
      error: '',
    };
  },
  methods: {
    createNew() {
      if (this.quote === '') {
        this.error = 'Please write a quote!';
        setTimeout(() => {
          this.error = '';
        }, 5000);
        return;
      } else {
        this.$emit('quoteAdded', this.quote);
        this.quote = '';
      }
    },
  },
};
</script>

<style scoped></style>
