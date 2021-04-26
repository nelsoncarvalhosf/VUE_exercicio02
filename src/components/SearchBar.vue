<template>
  <div>
    <form @submit.prevent="handleSearch">
      <p class="form-group">
        <label>Buscar:</label>
        <input class="form-control" type="text" v-model="search" />
      </p>
      <button class="btn btn-secondary float-right" type="submit">BUSCAR</button>
    </form>
    <div style="clear:both"></div>
    <hr style="border-color:#FFF">
  </div>
</template>

<script>
export default {
  props: {
    onSearch: Function,
  },
  data() {
    return {
      search: "",
    };
  },
  methods: {
    handleSearch() {
      this.onSearch(this.search);
    },
  },
};
</script>