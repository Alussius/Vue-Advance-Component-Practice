<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <button @click="selected = 'appQuote'">Quote</button>
        <button @click="selected = 'appAuthor'">Author</button>
        <button @click="selected = 'appNew'">New</button>
        <hr>
        <p>{{ selected }}</p>

        <!-- Commented out to introduce Dynamic Components -->
        <!-- <app-quote>
          < Passing as multiple slots to child component >
          <h2 slot="title">{{ quote.title }}</h2>
          <p slot="content">{{ quote.content }}</p>
        </app-quote> -->

        <!-- Dynamic Component -->
        <!-- Keeping Dynamic Components alive -->
        <keep-alive>
          <component :is="selected">
            <template v-if="selected == 'appQuote'">
              <h2 slot="title">{{ quote.title }}</h2>
              <p slot="content">{{ quote.content }}</p>
            </template>
          </component>
        </keep-alive>
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
      selected: 'appQuote'
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
