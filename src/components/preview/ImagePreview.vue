<template>
  <div class="card mb-3">
    <img :src="image.image_url" class="card-img-top" :alt="image.name" />
    <div class="card-body">
      <h5 class="card-title">{{ image.name }}</h5>
    </div>
  </div>
</template>

<script>
export default {
  name: "ImagePreview",
  props: ["image"],
  data() {
    return {};
  },
};
</script>

<style scoped>
.card {
  background: #1b263b;
  border-radius: 0px;
}

img {
  background: #fff;
  border-radius: 0px;
}

h5 {
  padding: 0;
  margin: 0;
}
</style>
