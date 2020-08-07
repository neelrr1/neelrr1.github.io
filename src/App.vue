<template>
  <div id="app" :class="dark ? 'dark' : 'light'">
    <br />
    <!-- <b-button class="float" @click="toggleDarkMode()">Toggle dark mode!</b-button> -->
    <div class="float p-1">  
      <b-form-checkbox v-model="dark" switch>Toggle Dark Mode!</b-form-checkbox>
    </div>
    <Home msg="Welcome to my site!" sub="(Definitely a WIP.)"/>
  </div>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'App',
  components: {
    Home
  },
  data: function () {
    return {
      dark: true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;  
  height: 100vh;
  transition: background 1s, color 1s;
  transition-timing-function: ease-out;
}

.dark {
  color: white;
  background: rgba(0, 0, 0, 0.86);
}

.float{
	position:fixed;
	bottom:40px;
	right:40px;
	background-color:#0C9;
	border-radius:50px;
	text-align:center;
}
</style>
