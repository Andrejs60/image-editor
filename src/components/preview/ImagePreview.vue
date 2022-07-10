<template>
  <div class="card mb-3">
    <img :src="image.data" class="card-img-top" :alt="image.name" />
    <div class="card-body">
      <h5 class="card-title">{{ image.name }}</h5>
      <p class="card-text">
        <small class="text-muted">Last updated 3 mins ago</small>
      </p>
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
img {
  /* border: 1px solid #000; */
}
</style>
