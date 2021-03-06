<template>
  <div class="projects">
    <div class="projects__wrapper">
      <h3>My Work</h3>
      <ul>
        <li class="project" v-for="(project, index) in projects" :key="index">
          <div class="project__img-container">
            <img src="https://via.placeholder.com/450x300" alt="">
          </div>
          <div class="project__text-container">
            <h4>{{ project.title }}</h4>
            <h5>{{ project.stack }}</h5>
            <p>{{ project.content }}</p>
            <a href="" v-for="(link, index) in project.links" :key="index">
              {{ link }}
            </a> 
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
      projects: []
    };
  },
  async created() {
    const projects = db.projects;

    this.projects = projects;
  }
};
</script>

<style lang="scss">
.projects {
  background-color: #000000;
  color: white;

  &__wrapper {
    max-width: 1280px;
    width: 75%;
    margin: 0 auto;

    h3 {
      text-align: center;
    }
  }

  .project {
    padding: 5% 0;
    display: flex;
    justify-content: center;
    align-items: center;

    &__text-container {
      padding: 0 8%;
      width: calc(50%);

      a {
        padding-right: 5%;
      }
    }

    &__img-container {
      width: calc(50%);

      img {
        width: 100%;
        height: 100%;
      }
    }
  }
}
</style>
