<template>
  <div id="app">
    <quoteform @quoteAdded="addNewQuote"/>
    <quoteList :quotes="quotes" @quoteDeleted="deleteQuote" />
  </div>
</template>

<script>
import QuoteForm from './components/QuoteForm';
import QuoteList from './components/QuoteList'
export default {
  name: 'app',
  data() {
    return {
      quotes: ['This is my first Quote'],
    }
  },
  components: {
    quoteform: QuoteForm,
    quoteList: QuoteList
  },
  methods: {
    addNewQuote(quote) {
      this.quotes.push(quote)
    },
    deleteQuote(index) {
      this.quotes.splice(index,1)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
