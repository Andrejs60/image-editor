<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/create">Create</router-link>
  </nav>
  <router-view />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
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
