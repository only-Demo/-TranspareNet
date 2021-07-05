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
    <div class="float-container">
    <div  class="float-child">
        <model-stl v-show="objType== 0" :src="`${publicPath}250ml.stl`" :height="600" :width="600" :cameraPosition=scale> </model-stl>
        <model-stl v-show="objType== 1" :src="`${publicPath}150ml.stl`" :height="600" :width="600" :cameraPosition=scale> </model-stl>
        <model-stl v-show="objType== 2" :src="`${publicPath}100ml.stl`" :height="600" :width="600" :cameraPosition=scale> </model-stl>
        <model-stl v-show="objType== 3" :src="`${publicPath}50mlflask.stl`" :height="600" :width="600" :cameraPosition=scale> </model-stl>
        <model-stl v-show="objType== 4" :src="`${publicPath}125mlflask.stl`" :height="600" :width="600" :cameraPosition=scale>  </model-stl>
        <model-stl v-show="objType== 5" :src="`${publicPath}250mlflask.stl`" :height="600" :width="600" :cameraPosition=scale> </model-stl>
    </div>
    <div  class="float-child">
        <model-ply v-show="objType== 0" :src="`${publicPath}depth_raw1.ply`" :height="600" :width="600" > </model-ply>
        <model-ply v-show="objType== 1" :src="`${publicPath}depth_raw1.ply`" :height="600" :width="600" > </model-ply>
        <model-ply v-show="objType== 2" :src="`${publicPath}depth_raw1.ply`" :height="600" :width="600" > </model-ply>
        <model-ply v-show="objType== 3" :src="`${publicPath}depth_raw1.ply`" :height="600" :width="600" > </model-ply>
        <model-ply v-show="objType== 4" :src="`${publicPath}depth_raw1.ply`" :height="600" :width="600" >  </model-ply>
        <model-ply v-show="objType== 5" :src="`${publicPath}depth_raw1.ply`" :height="600" :width="600"> </model-ply>
    </div>
    <div  class="float-child">
        <model-ply v-show="objType== 0" :src="`${publicPath}depth_ground1.ply`" :height="600" :width="600" > </model-ply>
        <model-ply v-show="objType== 1" :src="`${publicPath}depth_ground1.ply`" :height="600" :width="600" > </model-ply>
        <model-ply v-show="objType== 2" :src="`${publicPath}depth_ground1.ply`" :height="600" :width="600" > </model-ply>
        <model-ply v-show="objType== 3" :src="`${publicPath}depth_ground1.ply`" :height="600" :width="600" > </model-ply>
        <model-ply v-show="objType== 4" :src="`${publicPath}depth_ground1.ply`" :height="600" :width="600" >  </model-ply>
        <model-ply v-show="objType== 5" :src="`${publicPath}depth_ground1.ply`" :height="600" :width="600"> </model-ply>
    </div>
    </div>
    
  </div>

  
</template>

<script>
import GifViewer from './components/GifViewer.vue'
import { ModelStl, ModelPly } from 'vue-3d-model';
export default {
  name: 'App',
  components: {
    GifViewer,
    ModelStl,
    ModelPly
  },
  data (){
    return {
      objType: 0,
      publicPath: process.env.BASE_URL,
      scale: { x: 200, y: 0, z: -3 }
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
.container {
    height: 100%;
    width: 100%;
}
.float-child {
    width: 33%;
    float: left;
}  
</style>
