<template>
  <div class="create">
    <h1>Create new image</h1>
    <form @submit.prevent="createImage">
      <label>Name: </label>
      <input
        type="text"
        placeholder="Image name..."
        v-model="imageName"
        required
      />
      <label>Width: </label>
      <input type="number" min="100" max="500" v-model="width" required />
      <label>Height: </label>
      <input type="number" min="100" max="500" v-model="height" required />
      <button type="submit">Create</button>
    </form>
  </div>
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

<style></style>
