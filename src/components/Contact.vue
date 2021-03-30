<template>
  <div class="contact">
    <div class="contact__wrapper">
      <div class="contact__heading-container">
        <h2>Get In Touch</h2>
      </div>
      <div class="contact__text-container">
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Alias in architecto voluptatum exercitationem voluptate qui cum provident mollitia dolore officia.</p>
      </div>
      <ul class="contact__link-container">
        <li
          v-for="(item, index) in items" :key="index"
        >

        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import db from '../../db.json'

  export default {
    data() {
      return {
        links: []
      }
    },
    mounted() {
      console.log(db.personalInfo.links);
    },
  }
</script>

<style lang="scss">
@import '../styles/main.scss';

.contact {
  background-color: black;
  color: white;

  &__wrapper {
    max-width: 1280px;
    margin: 0 auto;
    padding: 5% 0;
  }

  &__heading-container {
    text-align: center;
  }

  &__text-container {
    width: 80%;
    margin: 0 auto;
  }
}
</style>