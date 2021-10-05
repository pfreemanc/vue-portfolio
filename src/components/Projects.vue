<template>
  <div class="projects" v-if="projects">
    <div class="projects__wrapper wrapper">
      <div class="projects__heading-container">
        <h3 class="projects--heading section--heading">Projects</h3>
      </div>

      <ul class="projects__container container" v-if="projects.length > 0">
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
            <hr class="project__line" />
            <a
              class="project--links"
              ref=""
              v-for="(link, index) in project.links"
              :key="index"
              :href="link"
            >
              {{ link }}
            </a>
          </div>
        </li>
      </ul>
    </div>

    <div class="svg--container">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1440 320"
        class="svg svg--black"
      >
        <path
          fill="#000000"
          fill-opacity="1"
          d="M0,128L80,154.7C160,181,320,235,480,218.7C640,203,800,117,960,106.7C1120,96,1280,160,1360,192L1440,224L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"
        ></path>
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    projects: {
      type: Array,
      required: true,
    },
  },
  async created() {},
}
</script>

<style lang="scss">
@import "../styles/_config.scss";

.projects {
  background-color: #000000;
  color: white;
  margin-top: -5px;

  &__heading-container {
    position: relative;

    .projects--heading {
      text-align: center;
      margin: 0;
    }

    .section--heading::before {
      background-color: white;
    }
  }

  &__container {
    // padding: 0 15%;
    margin: 0;

    // Mobile large
    @media (max-width: 414px) {
      // padding: 0 10%;
    }
  }

  .project {
    padding: 5% 0;
    display: flex;
    justify-content: center;
    align-items: center;

    // Tablet and below
    @media (max-width: 768px) {
      flex-direction: column;
      padding: 50px 0;
    }

    &__text-container {
      margin-left: auto;
      width: calc(45%);

      // Tablet and below
      @media (max-width: 768px) {
        margin-top: 20px;
        width: 100%;
      }

      .project {
        &--title {
          margin: 0 0 5px 0;
          font-size: clamp(2.4rem, 5vw, 3.2rem);
          font-weight: 500;
          font-family: $secondary-font;
        }

        &--stack {
          margin: unset;
          margin: 5px 0;
          font-weight: 300;
          font-size: 1.4rem;
        }

        &--content {
          margin: 5px 0 10px 0;
          font-family: $secondary-font;
          font-size: clamp(1.6rem, 5vw, 2rem);
        }

        &__line {
          margin-bottom: 10px;
        }

        &--links {
          padding-right: 5%;
          font-size: 1.8rem;
          font-weight: 300;
          color: $white;
        }
      }
    }

    &__img-container {
      width: calc(50%);

      // Tablet and below
      @media (max-width: 768px) {
        width: 90%;
      }

      img {
        width: 100%;
        height: 100%;
        border-radius: 20px;
      }
    }
  }
}
</style>
