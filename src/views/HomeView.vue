<template>
  <div class="home">
    <h1>Image Drawer</h1>
    <button @click="gotoCreate">Create new image</button>
    <h2>Saved Images</h2>
    <ImagePreviewGrid />
  </div>
</template>

<script>
import ImagePreviewGrid from "../components/preview/ImagePreviewGrid.vue";
export default {
  name: "HomeView",
  components: { ImagePreviewGrid },
  methods: {
    gotoCreate() {
      this.$router.push("/create");
    },
  },
};
</script>

<style scoped>
h1 {
  margin: 16px;
}
h2 {
  margin: 10px;
}
</style>
