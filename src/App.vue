<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <button @click="selectedComp = 'appQuote'">Quote</button>
        <button @click="selectedComp = 'appAuthor'">Author</button>
        <button @click="selectedComp = 'appNew'">New</button>
        <hr>
        <p>{{ selectedComp }}</p>
        <app-quote>
          <!-- Commented out to introduce Dynamic Components -->
          <!-- Passing as multiple slots to child component -->
          <!-- <h2 slot="title">{{ quote.title }}</h2>
          <p slot="content">{{ quote.content }}</p> -->

          <!-- Dynamic Component -->
          <component :is="selectedComp">
            <p>test</p>
          </component>
        </app-quote>
      </div>
    </div>
  </div>
</template>

<script>
import Quote from './components/Quote.vue';
import Author from './components/Author.vue';
import New from './components/New.vue';

export default {
  data() {
    return {
      quote: { title: 'Test Quote', content: 'A Wonderful Quote' },
      selectedComp: 'appQuote'
    }
  },
  components: {
    appQuote: Quote,
    appAuthor: Author,
    appNew: New
  }  
}
</script>

<style>
</style>
