<template>
  <div class="row col-12">
    <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
      <form>
        <div class="form-group">
          <textarea v-model="quote" class="form-control" rows="3" placeholder="Enter Your Quote...."/>
        </div>
        <div class="float-left col-sm-8 col-xs-12 col-md-4">
          <button type="submit" class="btn btn-primary btn-block" @click.prevent='addNewQuote' v-if="!isEditMode">Add New Quote</button>
          <button type="submit" class="btn btn-primary btn-block" @click.prevent='editQuote' v-else>Edit Quote</button>
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
      quote: this.currentQuote,
      isEditMode: !!this.currentQuote
    }
  },
  methods:{
    addNewQuote() {
      this.$emit('quoteAdded', this.quote)
      this.quote=''
    },
    editQuote() {
      this.$emit('quoteEdited', this.quote)
      this.quote='',
      this.isEditMode= false
    }
  },
  watch: {
    currentQuote(){
      this.quote=this.currentQuote,
      this.isEditMode= !!this.currentQuote
    },
  }

}
</script>

<style scoped>

</style>