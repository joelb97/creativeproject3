<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('Face Masks')" href="#" class="pure-menu-link">Face Masks</a></li>
      <li class="pure-menu-item"><a @click="select('Neck Gaiters')" href="#" class="pure-menu-link">Neck Gaiters</a></li>
    </ul>
  </div>
  <ProductList :products="products" />
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Browse',
  components: {
    ProductList
  },
  data() {
    return {
      type: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.type === this.type);
    }
  },
  methods: {
    select(type) {
      this.type = type.slice(0,-1);
    }
  }
}
</script>
