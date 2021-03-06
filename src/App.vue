<template>
  <div id="app">
    <Hero />
    <AboutMe />
    <Projects />
  </div>
</template>

<script>
import './styles/main.scss'
import Hero from './components/Hero.vue'
import AboutMe from './components/About-me.vue'
import Projects from './components/Projects.vue'

export default {
  name: 'App',
  components: {
    Hero,
    AboutMe,
    Projects
  }
}
</script>

<style lang="scss">
</style>
