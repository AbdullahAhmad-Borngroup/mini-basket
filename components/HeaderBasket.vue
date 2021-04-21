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
import PubSub from 'pubsub-js'
import { ADD_TO_BASKET } from '@/constants/'

export default {
  props: {
    brandId: String,
  },
  data() {
    return {
      numberOfItems: 0,
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
  mounted() {
    // create a function to subscribe to topics

    // add the function to the list of subscribers for a particular topic
    // we're keeping the returned token, in order to be able to unsubscribe
    // from the topic later on
    PubSub.subscribe(ADD_TO_BASKET, this.addToBasketSubscriber)
  },
  methods: {
    addToBasketSubscriber(msg, data) {
      this.numberOfItems = data
      console.log('This is basket page', msg, data)
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
