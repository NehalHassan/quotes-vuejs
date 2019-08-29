<template>
    <div class="quotes-loader row col-12">
        <div class="quotes" v-bind:style="{width: `${quotes.length*100 /10}%`}"></div>
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
    height: 15px;
    border-radius: 15px;
    background: gray;
    padding: initial;
    overflow: hidden;
    border: 1px solid gray;
    margin: 20px 0;
}
.quotes{
    background-color: #0062cc;
    height: 100%;
}
</style>