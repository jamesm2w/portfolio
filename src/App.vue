<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from './components/HelloWorld.vue'
import Slideshow from './components/Slideshow.vue';
</script>

<template>
  <img class="rounded-full shadow-md mx-auto hover:shadow-2xl transition-all duration-300 z-10 relative" width="350" alt="jamesm2w Profile Image" src="./assets/profileimage.png" />
  
  <Slideshow class="z-0" />
  
  <HelloWorld msg="Hello Vue 3 + Vite" />
</template>

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