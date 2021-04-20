<template>
  <div>
    <div class="toolbar">
      <div class="basket-icon-container">
        <HeaderBasket :brand-id="brandId" :number-of-items="2"></HeaderBasket>
      </div>
    </div>
  </div>
</template>

<script>
const DEFAULT_BRAND = '2'
export default {
  computed: {
    brandId() {
      return this.$route.query.brandId || DEFAULT_BRAND
    },
  },
}
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
