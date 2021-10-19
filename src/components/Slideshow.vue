<template>
    <div class="max-w-full absolute m-auto top-0 left-0 w-screen h-screen slideshow">

        <transition name="fade" mode="out-in">
            <img 
                v-if="index == 0"
                class="w-full h-full filter blur-sm" 
                src="./../assets/SlideshowBeach.jpg" 
                alt="Picture of a Beach"
            >

            <img
                v-else-if="index == 1"
                class="w-full h-full filter blur-sm" 
                src="./../assets/SlideshowClouds.jpg" 
                alt="Picture of clouds"
            >

            <img
                v-else-if="index == 2"
                class="w-full h-full filter blur-sm" 
                src="./../assets/SlideshowRocks.jpg" 
                alt="Picture of some rocks"
            >

            <img
                v-else-if="index == 3"
                class="w-full h-full filter blur-sm" 
                src="./../assets/SlideshowSea.jpg" 
                alt="Picture of the Sea"
            >
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
    transition: opacity 1s ease;
}

.fade-enter-from, .fade-leave-to {
    opacity: 0;
}

.slideshow img {
    object-fit: cover;
}

</style>