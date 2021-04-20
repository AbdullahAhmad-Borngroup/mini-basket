<template>
  <div>
    <div class="toolbar">
      <div class="basket-icon-container">
        <HeaderBasket :brand-id="1" :number-of-items="2"></HeaderBasket>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scopped>
.toolbar {
  display: flex;

  .basket-icon-container {
    margin: 15px;
    margin-left: auto;
  }
}
</style>
