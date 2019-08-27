<template>
    <div class="quotes-loader row col-12">
        <div class="quotes" v-bind:style="{width: 'calc(quotes*100) px'}"></div>
    </div>
</template>

<script>
export default {
    props: {
        quotes: Array
    }
}
</script>

<style scoped>
.quotes-loader{
    height: 50px;
}
.quotes{
    background-color: red;
    height: 100%;
}
</style>