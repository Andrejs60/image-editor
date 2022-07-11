<template>
  <div class="row row-cols-1 row-cols-md-4 g-4" v-if="images.length">
    <div class="col" v-for="image in images" :key="image.id">
      <ImagePreview :image="image" />
    </div>
  </div>
  <p v-else>No images available... (must also run "npm run db")</p>
</template>

<script>
import axios from "axios";
import ImagePreview from "./ImagePreview.vue";

export default {
  name: "ImagePreviewGrid",
  components: { ImagePreview },
  data() {
    return {
      images: [],
    };
  },
  mounted() {
    this.fetchImages();
  },
  methods: {
    async fetchImages() {
      const { data } = await axios.get("http://localhost:8000/api/images");
      this.images = data;
    },
  },
};
</script>

<style scoped>
.row {
  background: #0d1b2a;
  margin-top: 20px;
  border-radius: 12px;
}
p {
  margin: 20px;
}
</style>
