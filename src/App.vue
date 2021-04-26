<template>
  <div id="app" class="container">
    <img class="brand" alt="Vue logo" width="80px" src="./assets/logo.png">
    <h2 class="text-right">Shopping Cart: {{ product }}</h2>
    
    <SearchBar :onSearch="handleSearchProducts" />
    <ProductForm :changeValue="changeValue" />
    <ProductList :list="listSearch.length > 0 ? listSearch : list" />

  </div>
</template>

<script>
import SearchBar from "./components/SearchBar";
import ProductList from "./components/ProductList";
import ProductForm from "./components/ProductForm";

export default {
  name: "App",
  components: {
    ProductList,
    ProductForm,
    SearchBar,
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
          category: newValue.category,
        });
      },
    },
  },
  methods: {
    changeValue(newValue) {
      this.product = newValue;
    },
    handleSearchProducts(text) {
      const results = this.list.filter((p) => p.name == text);
      if (results.length > 0) {
        this.listSearch = results;
      } else {
        this.listSearch = this.list;
      }
    },
  },
  data() {
    return {
      list: [],
      listSearch: [],
    };
  },
};
</script>

<style lang="scss">
@import './assets/css/variables';
@import './assets/css/bootstrap';
</style>
