<template>
  <div class="row col-12">
    <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
      <form>
        <div class="form-group">
          <textarea v-model="quote" class="form-control" rows="3" placeholder="Enter Your Quote...."/>
        </div>
        <div class="float-left col-sm-8 col-xs-12 col-md-4">
          <button type="submit" class="btn btn-primary btn-block" @click.prevent='addNewQuote' v-if="!!!currentQuote">Add New Quote</button>
          <button type="submit" class="btn btn-primary btn-block" @click.prevent='editQuote' v-if="!!currentQuote">Edit Quote</button>
        </div>
      </form>
    </div>
  </div>

</template>

<script>
export default {
  props:{
    currentQuote: String,
  },
  data() {
    return {
      quote: ''
    }
  },
  methods:{
    addNewQuote() {
      this.$emit('quoteAdded', this.quote)
      this.quote=''
    }
  }
}
</script>

<style scoped>

</style>