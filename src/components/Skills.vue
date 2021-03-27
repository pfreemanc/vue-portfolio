<template>
  <div class="skills">
    <div class="skills__wrapper">
      <div class="skills__heading-container">
        <h2 class="skills--heading">
          Skills
        </h2>
      </div>
      <ul class="skills__container">
        <li
          v-for="(skill, index) in skills"
          :key="index"
          class="skill"
        >
          <div class="skill__image-container">
            <img :src="skill.imgSrc" alt="">
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import db from "../../db.json";

  export default {
    data() {
      return {
        skills: []
      }
    },
    mounted() {
      this.skills = db.skills;
    }
  }
</script>

<style lang="scss">
.skills {

  &__heading-container {
    text-align: center;
  }

  &__container {
    display: flex;
    flex-flow: row wrap;
    padding: 0 30px;

    .skill {
      list-style-type: none;
      width: 33%;
      padding: 10px;

      &__image-container {
        width: 100%;

        img {
          border-radius: 12px;
          width: 100%;
          height: 100%;
        }
      }
    }
  }
}
</style>