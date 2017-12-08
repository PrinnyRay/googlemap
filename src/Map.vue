<template>
  <div>
    <gmap-map
      v-bind:center="center"
      v-bind:zoom="9"
      style="width: 1024px; height: 768px"
    >
      <gmap-marker v-for="(m,i) in markers"
        v-bind:key="i"
        v-bind:position="m.position"
        v-bind:clickable="true"
        v-bind:draggable="true"
        v-on:click="center=m.position"
      ></gmap-marker>
    </gmap-map>
  </div>
</template>

<script>
  import * as VueGoogleMaps from 'vue2-google-maps';
  import Vue from 'vue';
 
  Vue.use(VueGoogleMaps, {
    load: {
      key: 'AIzaSyATFCJN2xUowYl5LhV2GrHx9CmP-OcRFqE',
      v: '3',
    }
  });
 
  export default {
    data () {
      return {
        center: {lat: 41.885080, lng: -87.624135},
        markers: [
        {position: {lat: 41.885080, lng: -87.624135}}, 
        {position: {lat: 41.831008, lng: -88.010101}}, 
        {position: {lat: 42.139287, lng: -88.056793}}, 
        {position: {lat: 42.002685, lng: -86.392365}}],
        place: null,
      }
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
</style>