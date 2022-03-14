<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('Playstation')" href="#" class="pure-menu-link">Playstation</a></li>
      <li class="pure-menu-item"><a @click="select('Xbox')" href="#" class="pure-menu-link">Xbox</a></li>
      <li class="pure-menu-item"><a @click="select('Nintendo')" href="#" class="pure-menu-link">Nintendo</a></li>
    </ul>
  </div>
  <ProductList :products="products" />
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'BrowseView',
  components: {
    ProductList
  },
  data() {
    return {
      platform: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.platform === this.platform);
    }
  },
  methods: {
    select(platform) {
      this.platform = platform;
    }
  }
}
</script>