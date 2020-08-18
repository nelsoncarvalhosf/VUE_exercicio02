<template>
  <div id="app" class="container">
    <img class="brand" alt="Vue logo" width="80px" src="./assets/logo.png">
    <h2 class="text-right">Shopping Cart: {{ product }}</h2>
    
    <ProductForm :changeValue="changeValue" />
    <ProductList :list="list" />
  </div>
</template>

<script>
import ProductList from "./components/ProductList";
import ProductForm from "./components/ProductForm";

export default {
  name: "App",
  components: {
    ProductList,
    ProductForm,
  },
  data() {
    return {
      list: [],
    };
  },
  computed: {
    product: {
      get: function() {
        return this.list.length;
      },
      set: function(newValue) {
        this.list = this.list.concat({
          name: newValue.name,
          price: newValue.price,
        });
      },
    },
  },
  methods: {
    changeValue(newValue) {
      this.product = newValue;
    },
  },
};
</script>

<style lang="scss">
@import './assets/css/variables';
@import './assets/css/bootstrap';
</style>
