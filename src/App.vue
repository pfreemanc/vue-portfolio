<template>
  <div id="app">
    <Hero
      v-if="Object.keys(personalInfo).length > 0"
      :personalInfo="personalInfo"
    />

    <AboutMe
      v-if="Object.keys(personalInfo).length > 0 && personalInfo.about"
      :aboutInfo="personalInfo.about"
    />

    <Projects v-if="projects" :projects="projects" />

    <Skills v-if="skills && skills.length > 0" :skills="skills" />
  </div>
</template>

<script>
import "./styles/main.scss"
import Hero from "./components/Hero.vue"
import AboutMe from "./components/About-me.vue"
import Projects from "./components/Projects.vue"
import Skills from "./components/Skills.vue"

import db from "../db.json"

export default {
  name: "App",
  components: {
    Hero,
    AboutMe,
    Projects,
    Skills,
  },
  data() {
    return {
      personalInfo: {},
      projects: [],
      skills: [],
    }
  },
  created() {
    for (const [key, value] of Object.entries(db)) {
      if (key === "personalInfo") {
        this.personalInfo = { ...value }
      } else if (key === "projects") {
        this.projects = [...value]
      } else if (key === "skills") {
        this.skills = [...value]
      }
    }
  },
}
</script>

<style lang="scss"></style>
