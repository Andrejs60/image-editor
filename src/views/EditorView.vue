<template>
  <h1>{{ imageName }}</h1>
  <CanvasEditor :width="width" :height="height" :imageName="imageName" />
</template>

<script>
import CanvasEditor from "../components/editor/CanvasEditor.vue";
export default {
  props: ["width", "height", "imageName"],
  components: { CanvasEditor },
};
</script>

<style></style>
