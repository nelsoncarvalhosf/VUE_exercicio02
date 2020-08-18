<template>
  <div id="list" class="row">
    <h1 class="title">Product List</h1>
    <li v-for="item in list" v-bind:key="item.name">
      <ProductItem :item="item" />
    </li>
  </div>
</template>

<script>
import ProductItem from "./ProductItem";

export default {
  components: {
    ProductItem,
  },
  props: {
    list: Array,
  },
  created() {
    console.log(this.list);
  },
};
</script>

<style scoped>
#list{
  border: #666 solid 2px;
  margin-top: 100px;
  padding: 30px;
}
.title{
  margin-top:-80px;
  margin-left: -30px;
}
li {
  color: black;
  list-style: none;
  width: 100%;
}
</style>
