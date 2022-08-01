<template>
  <nav>
    <router-link to="/">Home</router-link>
    |
    <router-link to="/posts">All Posts</router-link>
    |
    <router-link to="/posts/new">New Posts</router-link>
    |
    <router-link to="/about">About</router-link>
    |
    <router-link to="/test">Test</router-link>
    |
    <router-link to="/signup">Sign up</router-link>
    |
    <router-link to="/login">Log in</router-link>
    |
    <router-link to="/logout">Log out</router-link>
  </nav>
  <router-view />
  <footer><h1>FOOTS</h1></footer>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #21507f;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #5c80a4;
}

nav a.router-link-exact-active {
  color: #05e07e;
}
</style>
