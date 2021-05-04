<template>
  <div class="projects">
    <div class="projects__wrapper">
      <h3 class="projects--heading section--heading">Projects</h3>
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
import db from '../../db.json'

export default {
  data() {
    return {
      projects: [],
    }
  },
  async created() {
    const projects = db.projects

    this.projects = projects
  },
}
</script>

<style lang="scss">
@import '../styles/_config.scss';

.projects {
  // svg {
  //   background-color: white;
  //   margin-bottom: -5px;
  //   width: 101%;
  //   position: relative;
  //   left: -1px;
  // }

  // .svg--container {
  //   overflow: hidden;
  // }

  background-color: #000000;
  color: white;
  margin-top: -5px;

  &__wrapper {
    max-width: 1280px;
    margin: 0 auto;
    padding: 5% 0;

    .projects--heading {
      text-align: center;
      // font-size: clamp(3.6rem, 10vw, 9rem);
      margin: 0;
      // margin-bottom: 50px;
    }
  }

  &__container {
    padding: 0 15%;
    margin: 0;

    // Mobile large
    @media (max-width: 414px) {
      padding: 0 10%;
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

// Mobile small
@media (max-width: 320px) {
}
// Mobile
@media (max-width: 375px) {
}
// Mobile large
@media (max-width: 414px) {
}
// Tablet and below
@media (max-width: 768px) {
}
// Tablet Large
@media (max-width: 1024px) {
}
// MacBook Pro 13 inch
@media (max-width: 1280px) {
}
// MacBook Pro 15 inch
@media (max-width: 1440px) {
}
// MacBook Pro 16 inch
@media (min-width: 1792px) {
}
</style>
