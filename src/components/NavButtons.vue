<template>
  <div>
    <Button
        v-for="item in navitems"
        :key="item.name"

        @click="
        item.target.value.scrollIntoView({
            block: 'start',
            inline: 'nearest',
            behavior: 'smooth',
        });"
    >
        {{ item.name }}
    </Button>
  </div>
</template>
<script setup>
import Button from "./Button.vue";

defineProps({
    navitems: Array
});
</script>
