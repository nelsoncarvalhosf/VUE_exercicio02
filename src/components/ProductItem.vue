<template>
  <div class="item">
    <h2>{{ item.name }}</h2>
    <p class="price float-right">U$ {{ item.price }}</p>
  </div>
</template>

<script>
export default {
  props: {
    item: Object,
  },
};
</script>

<style scoped>
.item{
  width: 100%;
  display: block;
}
h2{
  color: black;
  width: 90%;
  border-bottom: dashed 1px #999;
  display: inline-block;
}
.price{
  color:white;
  width: 10%;
  display: inline-block;
  line-height: 60px;
}
</style>
