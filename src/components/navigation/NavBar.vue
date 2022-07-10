<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container-md">
      <router-link class="navbar-brand logo" exact-active-class="" to="/">{{
        title
      }}</router-link>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/create">Create</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      title: "Image Drawer",
    };
  },
};
</script>

<style scoped>
.logo {
  margin-right: 40px;
  color: white;
}

.navbar {
  background: #0d1b2a;
}

nav a {
  color: white;
  font-weight: bold;
}

.nav-link {
  padding: 4px 20px;
  margin: 0px 10px;
  font-weight: bold;
  border: none;
  border-radius: 8px;
  color: white;
}

.nav-link:hover {
  color: #fff;
  background: #e0e1dd32;
}

nav a.router-link-exact-active {
  background: #e0e1dd;
  color: #000;
}
</style>
