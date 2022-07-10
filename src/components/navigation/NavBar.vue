<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container-md">
      <router-link class="navbar-brand logo" exact-active-class="" to="/"
        ><i class="bi bi-easel"></i> Editor</router-link
      >
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
      <ul class="navbar-nav ml-auto">
        <li class="nav-item">
          <a class="nav-button" href="#"
            ><i class="bi bi-person-fill"></i> Login / Register</a
          >
        </li>
      </ul>
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
  margin-right: 60px;
  color: white;
  font-size: 23px;
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

.nav-button {
  padding: 8px;
  margin: 0px 4px;
  font-weight: bold;
  border: 2px solid #fff;
  border-radius: 8px;
  color: white;
  text-decoration: none;
}

.nav-button:hover {
  color: #0d1b2a;
  background: #fff;
}
</style>
