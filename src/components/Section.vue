<template>
  <div>
    <div class="text-center m-auto sm:w-full md:w-9/12 font-semibold text-5xl py-2" ref="sectionProjects">
      {{title}}
    </div>
    <p class="text-center m-auto sm:w-full md:w-9/12">
      {{ description }}
    </p>
    
    <slot></slot>

    <hr class="w-9/12 my-2 m-auto" />
  </div>
</template>
<script setup>

    defineProps({
        "title": String,
        "description": String
    })

</script>