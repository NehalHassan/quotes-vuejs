<template>
  <div class="row col-12">
    <quote v-for="(quote, index) in quotesArray" v-bind:key="index">
      {{quote}}
      <div class="quote-actions">
        <i class="fa fa-trash delete-quote" @click="deleteQuote(index)"></i>
        <i class="fa fa-edit edit-quote" @click="startEditing(index)"></i>
      </div>
    </quote>
  </div>
</template>

<script>
import QuoteCard from './QuoteCard';

export default {
  props:{
    quotes: Array
  },
  components: {
    quote: QuoteCard,
  },
  data(){
    return {
      quotesArray: this.quotes
    }
  },
  methods: {
    deleteQuote(index){
      this.$emit('quoteDeleted', index)
    },
    startEditing(index) {
      this.$emit('startEditing', index)
    }
  }
}
</script>

<style scoped>
.quote-actions {
  position: absolute;
    top: 0;
    right: 0;
}
i{
    font-size: 16px;
    padding: 4px 2px;
    margin: 4px 2px;
    cursor: pointer;
    color: #e6e6e6
}
.delete-quote:hover {
  color: red;
}
.edit-quote:hover {
  color: #0062cc;
}

</style>