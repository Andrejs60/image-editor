<template>
  <NavBar />
  <div class="container" style="height: 100vh">
    <router-view />
  </div>
</template>

<script>
import NavBar from "./components/navigation/NavBar.vue";
export default {
  components: { NavBar },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  background: #1b263b;
}

button {
  padding: 10px;
  margin: 0px 10px;
  background: #4ea8de;
  color: #fff;
  font-weight: bold;
  border: none;
  border-radius: 5px;
}

button:hover {
  background: #48bfe3;
  cursor: pointer;
}
</style>
