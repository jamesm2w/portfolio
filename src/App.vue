<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from './components/HelloWorld.vue'
import Slideshow from './components/Slideshow.vue';
</script>

<template>
  <img class="rounded-full shadow-md mx-auto hover:shadow-2xl transition-all duration-300 z-10 relative" width="250" alt="jamesm2w Profile Image" src="./assets/profileimage.png" />
  
  <Slideshow class="z-0" />
  
  <div class="sticky py-2 text-5xl font-thin w-full block text-white">jamesm2w</div>

  <div class="sticky py-4 text-xl font-medium block">
    Computer Scientist
  </div>
</template>

<style>
#app {
  font-family: 'Noto Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #DCDFE4;
  margin-top: 60px;
}

html {
  background-color: #282C34;
}
</style>

