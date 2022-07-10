<template>
  <form @submit.prevent="createImage">
    <div class="input-group mb-3">
      <span class="input-group-text">Name</span>
      <input
        type="text"
        class="form-control"
        placeholder="Name"
        v-model="imageName"
        required
      />
    </div>

    <div class="input-group mb-3">
      <span class="input-group-text">Width</span>
      <input
        type="number"
        class="form-control"
        min="100"
        max="500"
        v-model="width"
        required
      />
      <span class="input-group-text"> Height </span>
      <input
        type="number"
        class="form-control"
        min="100"
        max="500"
        v-model="height"
        required
      />
    </div>
    <button type="submit">Create</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      width: 100,
      height: 100,
      imageName: "",
    };
  },
  methods: {
    createImage() {
      this.$router.push({
        name: "editor",
        params: {
          width: this.width,
          height: this.height,
          imageName: this.imageName,
        },
      });
    },
  },
};
</script>

<style scoped>
form {
  margin: 0 auto;
  width: 400px;
}

button {
  padding: 10px;
  margin: 0px 10px;
  background: #415a77;
  color: #fff;
  font-weight: bold;
  border: none;
  border-radius: 5px;
}

button:hover {
  background: #778da9;
  cursor: pointer;
}
</style>
