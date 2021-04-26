<template>
  <div>
    <form @submit.prevent="onFormSubmit">
      <p class="form-group">
        <label>Name:</label>
        <input class="form-control" type="text" v-model="name" />
      </p>
      <p>{{ nameErrorMsg }}</p>

      <p class="form-group">
        <label>Price:</label>
        <input class="form-control" type="number" v-model="price" />
      </p>
      <p class="form-group">
        <label>Category:</label>
        <input class="form-control" type="text" v-model="category" />
      </p>
      <button class="btn btn-secondary float-right" type="submit">ADD</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      price: "",
      category: "",
      nameErrorMsg: "",
    };
  },
  props: {
    changeValue: Function,
  },
  watch: {
    name() {
      if (this.name.length >= 15) {
        this.nameErrorMsg =
          "The product name cannot exceed 15 characters";
      } else {
        this.nameError = "";
      }
    },
  },
  methods: {
    onFormSubmit() {
      this.changeValue({
        name: this.name,
        price: this.price,
        category: this.category,
      });
    },
  },
};
</script>
