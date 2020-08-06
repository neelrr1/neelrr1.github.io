<template>
  <div id="app">
    <br />
    <Home msg="Welcome to my site!" sub="(Definitely a WIP.)"/>
  </div>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  background: rgba(0, 0, 0, 0.86);
  height: 100vh;
}
</style>
