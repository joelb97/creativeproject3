<template>
<div>
  <h1>Your Cart</h1>
  <CartList :products="cart" />
  <p v-if="cartIsEmpty">Your Cart is empty</p>
</div>
</template>

<script>
import CartList from "../components/CartList.vue"
export default {
  name: 'Browse',
  components: {
    CartList
  },
  data() {
    return {
    }
  },
  computed: {
    cart() {
      return this.$root.$data.cart;
    },
    cartIsEmpty() {
      if (this.$root.$data.cart.length == 0) {
        return true;
      } else {
      return false;
      }
    }
  },
  methods: {
  }
}
</script>
