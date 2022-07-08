<template>
  <div class="home">
    <h1>Image Drawer</h1>
    <button @click="gotoCreate">Create new image</button>
    <h2>Saved Images</h2>
    <div class="images" v-if="images.length">
      <div class="image" v-for="image in images" :key="image.id">
        <img :src="image.data" alt="" />
        <p>{{ image.name }}</p>
      </div>
    </div>
    <p v-else>No images available...</p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HomeView",
  components: {},
  data() {
    return {
      images: [],
    };
  },
  mounted() {
    this.fetchImages();
  },
  methods: {
    gotoCreate() {
      this.$router.push("/create");
    },
    async fetchImages() {
      const { data } = await axios.get("http://localhost:3000/images");
      this.images = data;
    },
  },
};
</script>

<style scoped>
img {
  border: 1px solid #000;
}
</style>
