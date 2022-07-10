<template>
  <NavBar />
  <div class="container">
    <router-view />
  </div>
</template>

<script>
import NavBar from "./components/navigation/NavBar.vue";
export default {
  components: { NavBar },
};
</script>

<style></style>
