<template>
  <div class="row" id="app">
    <quotesBar :quotes="quotes"/>
    <quoteform
      v-if="quotes.length<10"
      @quoteAdded="addNewQuote"
      @quoteEdited="editQuote"
      :currentQuote="currentQuote"
    />

    <quoteList
      :quotes="quotes"
      @quoteDeleted="deleteQuote"
      @startEditing="startEditing"
    />

    <div class="row col-12">
      <div class="alert alert-primary col-12" v-if="!quotes.length">Add new quotes to your list</div>
      <div class="alert alert-warning col-12" v-if="quotes.length>=10">delete quotes to add new one</div>
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
      currentQuote: '',
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
    },
    editQuote(quote) {
      this.quotes[this.currenQuoteIndex] = quote;
    },
    startEditing(index) {
      this.currentQuote = this.quotes[index]
      this.currenQuoteIndex = index;
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
