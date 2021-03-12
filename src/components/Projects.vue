<template>
  <div class="projects">
    <div class="projects__wrapper">
      <h3 class="projects--heading">My Work</h3>
      <ul>
        <li class="project" v-for="(project, index) in projects" :key="index">
          <div class="project__img-container">
            <img src="https://via.placeholder.com/450x300" alt="">
          </div>
          <div class="project__text-container">
            <h4 class="project--title">{{ project.title }}</h4>
            <h5 class="project--stack">{{ project.stack }}</h5>
            <p class="project--content">{{ project.content }}</p>
            <a  class="project--links" href="" v-for="(link, index) in project.links" :key="index">
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
  margin-top: -5px;

  &__wrapper {
    max-width: 1280px;
    margin: 0 auto;
    padding: 5% 10%;


    .projects--heading {
      text-align: center;
      font-size: clamp(3.6rem, 10vw, 9rem);
    }
  }

  .project {
    padding: 5% 0;
    display: flex;
    justify-content: center;
    align-items: center;

    @media (max-width: 768px) // Tablet and below (most iPads) 
      {
        flex-direction: column;
      }

    &__text-container {
      padding-left: 8%;
      width: calc(50%);

      @media (max-width: 768px) // Tablet and below (most iPads) 
        {
          width: 100%;
        }
      .project {

        &--title {
          margin: 0 0 10px 0;
          font-size: clamp(2.4rem, 3vw, 4rem);
        }

        &--links {
          padding-right: 5%;
        }
      }
    }

    &__img-container {
      width: calc(50%);

      @media (max-width: 768px) // Tablet and below (most iPads) 
      {
        width: 80%;
      }

      img {
        width: 100%;
        height: 100%;
      }
    }
  }
}

@media (max-width: 320px) // Mobile small (iPhone SE original) and below [very rare now] 
{}
@media (max-width: 375px) // Mobile (iPhone Regular) and below 
{}
@media (max-width: 414px) // Mobile large (iPhone Max) and below 
{}
@media (max-width: 768px) // Tablet and below (most iPads) 
{}
@media (max-width: 1024px) // Tablet Large and below (iPad Pro 12.9-inch) 
{}
@media (max-width: 1280px) // MacBook Pro 13 inch and below 
{}
@media (max-width: 1440px) // MacBook Pro 15 inch and below 
{}
@media (min-width: 1792px) // MacBook Pro 16 inch and above 
{}
</style>
