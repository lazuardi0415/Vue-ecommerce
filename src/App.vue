<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Lato, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: crimson;
}

#nav a.router-link-exact-active {
  color: lightcoral;
}
</style>
