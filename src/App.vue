<template>
  <div id="app" class="bg-secondary">

    <img alt="Vue logo" src="./assets/logo.png">
    
    <p1 smg="curso p1 a p3"  />
    <color/>
    <gym/>
    <cpadre/>
  </div>
</template>

<script>

import p1 from './components/p1.vue';
import color from './components/color.vue';
import gym from './components/gym.vue';
import cpadre from './components/cpadre.vue';




export default {
  name: 'app',
  components: {
    p1,
    color,
    gym,
    cpadre
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
  margin-top: 60px;
}
</style>
