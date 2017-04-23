<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
import Vue from 'vue'

export default {
  name: 'app'
}
</script>

<style>
html,body{
  margin: 0;
  padding: 0;
  height: 100%;
}
button::-moz-focus-inner {
  border: 0;
} 
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100%;
  height: 100%;
}
</style>
