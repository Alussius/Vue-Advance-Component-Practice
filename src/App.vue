<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <app-quote>
          <!-- Passing as multiple slots to child component -->
          <h2 slot="title">{{ quote.title }}</h2>
          <p slot="content">{{ quote.content }}</p>
        </app-quote>
      </div>
    </div>
  </div>
</template>

<script>
import Quote from './components/Quote.vue';

export default {
  data() {
    return {
      quote: { title: 'Test Quote', content: 'A Wonderful Quote' }
    }
  },
  components: {
    appQuote: Quote
  }  
}
</script>

<style>
</style>
