<template>
  <div class="projects">
    <div class="projects__wrapper">
      <h3 class="projects--heading">My Work</h3>
      <ul class="projects__container">
        <li class="project" v-for="(project, index) in projects" :key="index">
          <div class="project__img-container">
            <img src="https://via.placeholder.com/450x300" alt="" />
          </div>
          <div class="project__text-container">
            <h4 class="project--title">{{ project.title }}</h4>
            <h5 class="project--stack">
              <span>Built With: </span>{{ project.stack }}
            </h5>
            <p class="project--content">{{ project.content }}</p>
            <a
              class="project--links"
              ref=""
              v-for="(link, index) in project.links"
              :key="index"
            >
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
@import "../styles/_config.scss";

.projects {
  background-color: #000000;
  color: white;
  margin-top: -5px;

  &__wrapper {
    max-width: 1280px;
    margin: 0 auto;
    padding: 5% 0;

    .projects--heading {
      text-align: center;
      font-size: clamp(3.6rem, 10vw, 9rem);
    }
  }

  &__container {
    padding: 0 10%;
  }

  .project {
    padding: 5% 0;
    display: flex;
    justify-content: center;
    align-items: center;

    &:nth-of-type(even) {
      .project__text-container {
        order: 1;
      }
      .project__img-container {
        order: 2;
      }
    }

    // Tablet and below
    @media (max-width: 768px) {
      flex-direction: column;
    }

    &__text-container {
      padding-left: 8%;
      width: calc(50%);

      @media (max-width: 768px) {
        width: 100%;
      }

      .project {
        &--title {
          margin: 0 0 5px 0;
          font-size: clamp(2.4rem, 5vw, 3.2rem);
          font-weight: 700;
          font-family: $secondary-font;
        }

        &--stack {
          margin: unset;
          margin: 5px 0;
          font-weight: 300;
          font-size: 1.6rem;
        }

        &--content {
          margin: 20px 0;
          font-family: $secondary-font;
          font-size: 2rem;
        }

        &--links {
          padding-right: 5%;
          font-size: 1.8rem;
          font-weight: 300;
        }
      }
    }

    &__img-container {
      width: calc(50%);

      @media (max-width: 768px) {
        width: 80%;
      }

      img {
        width: 100%;
        height: 100%;
      }
    }
  }
}
</style>
