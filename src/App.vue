<template>
  <Slideshow class="z-0" />

  <div ref="topSection" class="h-screen w-screen">
    <img
      class="
        rounded-full
        shadow-md
        mx-auto
        hover:shadow-2xl
        transition-all
        duration-300
        relative
      "
      width="250"
      alt="jamesm2w Profile Image"
      src="./assets/profileimage.png"
    />

    <div
      class="sticky py-2 text-5xl font-thin w-full block text-white font-mono"
    >
      jamesm2w
    </div>

    <div class="sticky py-4 text-xl font-medium block">Computer Scientist from Dorset, UK</div>

    <Button @click="
        $refs.projectSection.scrollIntoView({
          block: 'start',
          inline: 'nearest',
          behavior: 'smooth',
        })
      ">View Projects</Button>
  </div>

  <div ref="projectSection" class="min-h-screen w-screen">
    <Button
      @click="
        $refs.topSection.scrollIntoView({
          block: 'start',
          inline: 'nearest',
          behavior: 'smooth',
        })
      "
      >Top</Button
    >
    <Button
      @click="
        $refs.sectionProjects.scrollIntoView({
          block: 'start',
          inline: 'nearest',
          behavior: 'smooth',
        })
      "
      >Projects</Button
    >
    <Button
      @click="
        $refs.sectionCoursework.scrollIntoView({
          block: 'start',
          inline: 'nearest',
          behavior: 'smooth',
        })
      "
      >Coursework</Button
    >
    <Button
      @click="
        $refs.socialLinks.scrollIntoView({
          block: 'start',
          inline: 'nearest',
          behavior: 'smooth',
        })
      "
      >Contact</Button
    >

    <div class="font-mono font-semibold text-5xl">Technologies</div>
    <div class="flex flex-row flex-wrap w-9/12 justify-center m-auto">
      <Pill v-for="language in projectData.languages" :key="language">
        {{ language }}
      </Pill>
    </div>

    <hr class="w-9/12 my-2 m-auto">

    <div class="font-mono font-semibold text-5xl" ref="sectionProjects">
      Projects
    </div>
    <Button class="text-sm" @click="
        $refs.projectSection.scrollIntoView({
          block: 'start',
          inline: 'nearest',
          behavior: 'smooth',
        })
      ">Top</Button>
    <div class="w-10/12 hero m-auto pb-10">
      <Project
        v-for="project in projectData.projects"
        :key="project.name"
        v-bind="project"
      ></Project>
    </div>

    <hr class="w-9/12 my-2 m-auto">

    <div class="font-mono font-semibold text-5xl" ref="sectionCoursework">
      Coursework
    </div>
    <Button class="text-sm" @click="
        $refs.projectSection.scrollIntoView({
          block: 'start',
          inline: 'nearest',
          behavior: 'smooth',
        })
      ">Top</Button>
    <div class="w-10/12 hero m-auto pb-10">
      <Project
        v-for="project in projectData.coursework"
        :key="project.name"
        v-bind="project"
      ></Project>
    </div>

    <hr class="w-9/12 my-2 m-auto">

    <div class="font-mono font-semibold text-4xl" ref="socialLinks">
      Contact & Links
    </div>

    <Button class="text-sm" @click="
        $refs.projectSection.scrollIntoView({
          block: 'start',
          inline: 'nearest',
          behavior: 'smooth',
        })
      ">Top</Button>
    
    <div class="flex flex-row flex-wrap w-9/12 justify-center m-auto">
      <Pill v-for="linkObj in projectData.socialLinks" :key="linkObj.name">
        <a :href="linkObj.url" target="_blank">{{ linkObj.name }}</a>
      </Pill>
    </div>
  </div>
  <div class="bg-gray-900 h-10 py-2 mt-2">
    <span class="float-left font-mono ml-2">Copyright (C) James Macer-Wright {{ (new Date()).getYear() }}</span>
    <span class="float-right font-mono mr-2 underline"><a target="_blank" href="https://github.com/jamesm2w/jamesm2w.github.io">Source (Github)</a></span>
  </div>
</template>
<script setup>
import Button from "./components/Button.vue";
import Pill from "./components/Pill.vue";
import Slideshow from "./components/Slideshow.vue";
import Project from "./components/Project.vue";

import * as projectData from "./assets/projects.json";

console.log(projectData.projects);
</script>

<style>
#app {
  font-family: "Noto Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #dcdfe4;
  margin-top: 60px;
}

html {
  background-color: #282c34;
  overflow-x: hidden;
}

.hero {
  display: grid;
  align-items: flex-start;
  grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
  grid-gap: .5rem;
}
</style>

