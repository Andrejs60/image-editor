<template>
  <div class="home">
    <h1>Image Editor</h1>
    <button @click="gotoCreate">Create new image</button>
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

<style></style>
