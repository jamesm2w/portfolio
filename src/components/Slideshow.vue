<template>
    <div class="max-w-full absolute m-auto top-0 left-0 w-screen h-screen">
        <transition name="fade">
            <div v-show="index == 0" class="transition-all duration-700">
                <img class="w-full" src="./../assets/SlideshowBeach.jpg" alt="Picture of a Beach">
                <div class="text">Image Credit: James Macer-Wright</div>
            </div>
        </transition>
        <transition name="fade">
            <div v-show="index == 1" class="transition-all duration-700">
                <img class="w-full" src="./../assets/SlideshowClouds.jpg" alt="Picture of clouds">
                <div class="text">Image Credit: James Macer-Wright</div>
            </div>
        </transition>
        <transition name="fade">
            <div v-show="index == 2" class="transition-all duration-700">
                <img class="w-full" src="./../assets/SlideshowRocks.jpg" alt="Picture of some rocks">
                <div class="text">Image Credit: James Macer-Wright</div>
            </div>
        </transition>
        <transition name="fade">
            <div v-show="index == 3" class="transition-all duration-700">
                <img class="w-full" src="./../assets/SlideshowSea.jpg" alt="Picture of the Sea">
                <div class="text">Image Credit: James Macer-Wright</div>
            </div>
        </transition>
    </div>    
</template>

<script setup>
import { ref } from "@vue/reactivity";

let index = ref(0);

function incrementIndex () {
    index.value++;
    index.value = index.value % 4;
}
setInterval(incrementIndex, 5000);
</script>
<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: all 1s ease-in-out;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
  transition: all 1s ease-in-out;
}

.fade-enter-to, .fade-leave {
    opacity: 1;
    transition: all 1s ease-in-out;
}
</style>