<template>
  <div class="row card float-left">
    <slot></slot>
  </div>
</template>

<style scoped>
.card {
  width: 250px;
    background: #ffffff;
    min-height: 100px;
    padding: 16px;
    border: 1px solid #e6e6e6;
    color: #333;
    box-shadow: 0px 0px 6px 2px #e6e6e6;
    margin: 10px;
    border-radius: 2px;
    display: inline-block;
    font-family: Arizonia;
    text-align: left
}
</style>