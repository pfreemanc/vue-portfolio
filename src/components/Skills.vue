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
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320" class="svg">
      <path
        fill="#000000"
        fill-opacity="1"
        d="M0,128L80,154.7C160,181,320,235,480,218.7C640,203,800,117,960,106.7C1120,96,1280,160,1360,192L1440,224L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"
      ></path>
    </svg>
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

  svg {
    transform: rotate(180deg);
    margin-bottom: -5px;
  }

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