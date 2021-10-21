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

    <div class="sticky py-4 text-xl font-medium block">
      Computer Scientist from Dorset, UK
    </div>

    <Button
      @click="
        $refs.projectSection.scrollIntoView({
          block: 'start',
          inline: 'nearest',
          behavior: 'smooth',
        })
      "
      >View Projects</Button
    >
  </div>

  <div ref="projectSection" class="min-h-screen w-screen">
    <NavButtons
      :navitems="navItems"
      class="
        sticky
        top-3
        flex
        sm:flex-row
        flex-wrap
        justify-center
        md:flex-col md:float-left
        ml-3
        py-3  
      "
      style="background-color: #282c34;"
    ></NavButtons>

    <div ref="sectionTechnology"></div>
    <Section
      title="Languages"
      description="All the programming technologies I have some experience working with.
      However, I'm always up for a new challenge and to learn new languages as
      they're required by the project I'm working on."
    >
      <div class="flex flex-row flex-wrap w-9/12 justify-center m-auto">
        <Pill v-for="language in projectData.languages" :key="language">
          {{ language }}
        </Pill>
      </div>
    </Section>

    <div ref="sectionProjects"></div>
    <Section
      title="Projects"
      description="Personal Projects which have been of finished enough to publish on the
      internet. Most are in various states of completion, if you want me to work
      on something just contact me and I'll see if I can do it. Alternatively,
      create a pull request :)"
    >
      <div class="w-10/12 hero m-auto pb-10">
        <Project
          v-for="project in projectData.projects"
          :key="project.name"
          v-bind="project"
        ></Project>
      </div>
    </Section>

    <div ref="sectionCoursework"></div>
    <Section
      title="Coursework"
      description="Coursework/Graded Projects from school and university, which I have
      completed and wanted to make a note of. In most cases the source code can
      not be published as the task could be reused."
    >
      <div class="w-10/12 hero m-auto pb-10">
        <Project
          v-for="project in projectData.coursework"
          :key="project.name"
          v-bind="project"
        ></Project>
      </div>
    </Section>

    <div ref="socialLinks"></div>
    <Section title="Contact & Links" description="Contact Me!">
      <div class="flex flex-row flex-wrap w-9/12 justify-center m-auto">
        <Pill v-for="linkObj in projectData.socialLinks" :key="linkObj.name">
          <a :href="linkObj.url" target="_blank">{{ linkObj.name }}</a>
        </Pill>
      </div>
    </Section>
  </div>
  <div class="bg-gray-900 min-h-10 py-2 mt-2">
    <span class="float-left font-mono ml-2"
      >Copyright (C) James Macer-Wright {{ new Date().getFullYear() }}</span
    >
    <span class="float-right font-mono mr-2 underline"
      ><a target="_blank" href="https://github.com/jamesm2w/jamesm2w.github.io"
        >Source (Github)</a
      ></span
    >
    <div class="clear-both"></div>
  </div>
</template>
<script setup>
import Button from "./components/Button.vue";
import Pill from "./components/Pill.vue";
import Slideshow from "./components/Slideshow.vue";
import Project from "./components/Project.vue";
import Section from "./components/Section.vue";
import NavButtons from "./components/NavButtons.vue";

import { ref } from "vue";

import * as projectData from "./assets/projects.json";

console.log(projectData.projects);

const topSection = ref(null);
const projectSection = ref(null);

const sectionTechnology = ref(null);
const sectionProjects = ref(null);
const sectionCoursework = ref(null);
const socialLinks = ref(null);

const navItems = [
  { name: "Top", target: topSection },
  { name: "Languages", target: sectionTechnology },
  { name: "Projects", target: sectionProjects },
  { name: "Coursework", target: sectionCoursework },
  { name: "Contact", target: socialLinks },
];
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
  grid-gap: 0.5rem;
}
</style>

