<template>
  <div>
    <link
      v-if="brandCssLink"
      rel="stylesheet"
      :href="brandCssLink"
      type="text/css"
    />
    <div class="mini-basket-wrapper">
      <tef-icon cloak icon="cart" size="xl"></tef-icon>
      <span class="number-of-items">{{ numberOfItems }}</span>
    </div>
    <script :src="iconComponentLink"></script>
    <script :src="occlLink"></script>
  </div>
</template>

<script>
export default {
  props: {
    brandId: String,
    numberOfItems: Number,
  },
  data() {
    return {
      title: 'Hi',
    }
  },
  computed: {
    // eslint-disable-next-line object-shorthand
    brandCssLink() {
      return `https://library.telefonica.de/${this.brandId}/v1.5.0/components/theme/bundle.css`
    },
    iconComponentLink() {
      return `https://library.telefonica.de/${this.brandId}/v1.5.0/components/icon/bundle.js`
    },
    occlLink() {
      return `https://library.telefonica.de/${this.brandId}/v1.5.0/library/vendors.js`
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
    width: 15px;
    height: 15px;
    font-size: 11px;
    text-align: center;
  }
}
</style>
