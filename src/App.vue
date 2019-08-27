<template>
  <div class="row" id="app">
    <quotesBar :quotes="quotes"/>
    <quoteform @quoteAdded="addNewQuote"/>
    <quoteList :quotes="quotes" @quoteDeleted="deleteQuote" />
    <div class="row col-12">
      <div class="alert alert-primary col-12" v-if="!quotes.length">Add new quotes to your list</div>
      <div class="alert alert-warning col-12" v-if="quotes.length>10">delete quotes to add new one</div>
    </div>
  </div>
</template>

<script>
import QuoteForm from './components/QuoteForm';
import QuoteList from './components/QuoteList';
import QuotesBar from './components/QuotesBar';

export default {
  data() {
    return {
      quotes: ['This is my first Quote'],
    }
  },
  components: {
    quoteform: QuoteForm,
    quoteList: QuoteList,
    quotesBar: QuotesBar
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

body{
  overflow-x: hidden;
  width: 100%;
  padding: 0 60px;
}


</style>
