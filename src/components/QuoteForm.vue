<template>
  <div class="row">
    <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
      <form>
        <div class="form-group">
          <textarea v-model="quote" class="form-control" rows="3" placeholder="Enter Your Quote...."/>
        </div>
        <div class="float-left col-sm-8 col-xs-12 col-md-4">
          <button type="submit" class="btn btn-primary btn-block" @click.prevent='addNewQuote'>Add New Quote</button>
        </div>
      </form>
    </div>
  </div>

</template>

<script>
export default {
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