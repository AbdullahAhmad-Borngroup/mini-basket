<template>
  <div class="mini-basket-wrapper">
    <link
      v-if="brandCssLink"
      rel="stylesheet"
      :href="brandCssLink"
      type="text/css"
    />
    <tef-icon cloak icon="cart" size="xl"></tef-icon>
    <span class="number-of-items">{{ numberOfItems }}</span>
  </div>
</template>

<script>
export default {
  props: {
    brandId: Number,
    numberOfItems: Number,
  },
  data() {
    return {
      title: 'Hi',
    }
  },
  computed: {
    // eslint-disable-next-line object-shorthand
    brandCssLink: function () {
      return `https://library.telefonica.de/${this.brandId}/v1.5.0/components/theme/bundle.css`
    },
  },
}
</script>

<style lang="scss" scoped>
.mini-basket-wrapper {
  position: relative;
  color: var(--color-brand--brand-2);
  .number-of-items {
    color: #ffffff;
    position: absolute;
    right: 2px;
    background-color: #7814b3;
    border-radius: 50%;
    padding: 2px;
    width: 15px;
    height: 15px;
    font-size: 11px;
    text-align: center;
  }
}
</style>
