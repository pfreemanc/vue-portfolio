<template>
  <div id="app">
    <Hero />
    <AboutMe />
    <Projects />
    <Skills />
  </div>
</template>

<script>
import "./styles/main.scss"
import Hero from "./components/Hero.vue"
import AboutMe from "./components/About-me.vue"
import Projects from "./components/Projects.vue"
import Skills from "./components/Skills.vue"

export default {
  name: "App",
  components: {
    Hero,
    AboutMe,
    Projects,
    Skills,
  },
}
</script>

<style lang="scss"></style>
