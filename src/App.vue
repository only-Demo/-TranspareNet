<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <gif-viewer msg="test"></gif-viewer>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import GifViewer from './components/GifViewer.vue'
export default {
  name: 'App',
  components: {
    HelloWorld,
    GifViewer
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
