<template>
  <div id="app" >
    <div id="example-5">
      <span>Object Type:</span>
      <select v-model="objType">
        <option value=0>Beaker 0</option>
        <option value="1">Beaker 1</option>
        <option value="2">Beaker 2</option>
        <option value="3">Flask 0</option>
        <option value="4">Flask 1</option>
        <option value="5">Flask 2</option>
      </select>
    </div>
    <div class="float-container">
    <div id="imageGif"  class="float-child">
      <gif-viewer v-show="objType == 0" file="image0.gif"></gif-viewer>
      <gif-viewer v-show="objType == 1" file="image1.gif"></gif-viewer>
      <gif-viewer  v-show="objType == 2" file="image2.gif"></gif-viewer>
      <gif-viewer v-show="objType == 3 || objType == 5" file="image53.gif"></gif-viewer>
      <gif-viewer v-show="objType == 4" file="image24.gif"></gif-viewer>
    </div>
    <div id="depthGif"  class="float-child">
      <gif-viewer v-show="objType == 0" file="depth0.gif"></gif-viewer>
      <gif-viewer v-show="objType == 1" file="depth1.gif"></gif-viewer>
      <gif-viewer v-show="objType == 2" file="depth2.gif"></gif-viewer>
      <gif-viewer v-show="objType == 3 || objType == 5" file="depth53.gif"></gif-viewer>
      <gif-viewer v-show="objType == 4" file="depth24.gif"></gif-viewer>
    </div>
    <div id="depthGTGif"  class="float-child">
      <gif-viewer v-show="objType== 0" file="depthgt0.gif"></gif-viewer>
      <gif-viewer v-show="objType == 1" file="depthgt1.gif"></gif-viewer>
      <gif-viewer v-show="objType == 2" file="depthgt2.gif"></gif-viewer>
      <gif-viewer v-show="objType == 3 || objType == 5" file="depthgt53.gif"></gif-viewer>
      <gif-viewer v-show="objType == 4" file="depthgt24.gif"></gif-viewer>
    </div>
    </div>
    <model-stl src="`${publicPath}gear.stl`"></model-obj>
  </div>

  
</template>

<script>
import GifViewer from './components/GifViewer.vue'
import { ModelStl } from 'vue-3d-model';
export default {
  name: 'App',
  components: {
    GifViewer,
    ModelStl 
  },
  data (){
    return {
      objType: 0,
      publicPath: process.env.BASE_URL
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
  color: #2c3e50;
  margin-top: 60px;
}
.float-container {
    padding: 20px;
}

.float-child {
    width: 33%;
    float: left;
}  
</style>
