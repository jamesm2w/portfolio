<template>
    <div class="
      rounded-xl
      py-4
      px-6
      ml-3
      my-2
      border-2
      w-full
      h-full
      bg-gray-100
      text-black

      flex
      flex-col
      shadow-md
    ">
        <div class="flex flex-row justify-start flex-wrap" v-if="languages.length > 0">
            <span class="rounded-md px-2 py-2 mr-2 text-xs bg-blue-200 text-blue-700" v-for="language of languages"
                :key="language">{{ language }}</span>
        </div>

        <span class="block font-semibold text-lg text-left">{{ name }}
            <span class="font-extralight text-sm" v-if="date != ''">({{ date }})</span></span>
        <span class="block text-left font-light text-sm">{{ description }}</span>

        <div class="mt-auto">
            <hr class="my-2" />
            <div class="flex flex-row justify-center flex-wrap" v-if="links.length > 0">
                <a v-for="link in links" :key="link.name" :href="link.url" target="_blank"
                    class="rounded-lg shadow-sm hover:bg-blue-600 hover:text-blue-200 transition-colors duration-100 hover:shadow-md bg-blue-200 text-blue-700 py-2 px-5 mx-2 my-2">{{ link.name }}</a>
            </div>
        </div>
        
    </div>
</template>
<script setup>
import Pill from "./Pill.vue";
const props = defineProps({
    name: String,
    date: String,
    links: Array,
    description: String,
    languages: Array,
});
</script>
<style scoped>
</style>