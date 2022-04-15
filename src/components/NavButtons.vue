<template>
    <div ref="target" class="
	  sticky
	  top-0
	  flex
	  flex-row
      flex-wrap
      gap-2
	  justify-center
	  py-3
	" :class="{stuck}" style="top: -2px;">

        <Button v-for="item in navitems" :key="item.name" class="rounded-lg shadow-md text-white" @click="
        item.target.value.scrollIntoView({
            block: 'start',
            inline: 'nearest',
            behavior: 'smooth',
        });">
            {{ item.name }}
        </Button>
    </div>
</template>
<script setup>
import { onMounted, ref } from "vue";
import Button from "./Button.vue";

const props = defineProps({
    navitems: Array
});

const stuck = ref(false);
const target = ref();

onMounted(() => {
    const observer = new IntersectionObserver(
        ([e]) => {
            stuck.value = !e.isIntersecting;
        },
        { 
            //root: document.querySelector("div[project-section]"),
            threshold: [0.99] 
        }
    );
    observer.observe(target.value);
});
</script>
<style scoped>
div.stuck {
    @apply bg-slate-700;
}
</style>
