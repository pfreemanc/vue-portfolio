<template>
  <div class="about-me">
    <div class="about-me__wrapper">
      <div class="about-me__image-container">
        <img src="../assets/meagain.jpg" alt="" />
      </div>
      <div class="about-me__text-container">
        <h3 class="about-me--heading">
          {{ heading }}
        </h3>
        <p class="about-me--content">
          {{ content }}
        </p>
      </div>
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
      content: "",
      heading: ""
    };
  },
  async created() {
    const aboutMe = await db.personalInfo.about;
    this.content = aboutMe.content;
    this.heading = aboutMe.heading;
  }
};
</script>

<style lang="scss">
@import "../styles/_config.scss";

.about-me {

  &__wrapper {
    max-width: 1280px;
    margin: 0 auto;
    padding: 15% 10% 5% 10%;
  }

  &__image-container {
    width: 50%;
    margin: 0 auto;
    img {
      width: 100%;
      border-radius: 50%;
    }
  }

  &__text-container {
    padding: 0 10%;

    .about-me--heading {
      font-size: clamp(2.4rem, 4vw, 4.6rem);
    }

    .about-me--content {
      font-size: clamp(1.4rem, 5vw, 2.8rem);
      font-family: $secondary-font;
    }
  }

  .svg {
    transform: rotate(180deg);
  }
  @media (max-width: 320px) // Mobile small (iPhone SE original) and below [very rare now] 
  {}
  @media (max-width: 375px) // Mobile (iPhone Regular) and below 
  {}
  @media (max-width: 414px) // Mobile large (iPhone Max) and below 
  {
    .about-me {
      &__text-container {
        padding: 0;
      }

      &__image-container {
        width: 80%;
      }
    }
  }
  @media (max-width: 768px) // Tablet and below (most iPads) 
  {
    .about-me {

      &__text-container {
        padding: 0 5%;
        margin: 0 auto;
      }
    }
  }
  @media (max-width: 1024px) // Tablet Large and below (iPad Pro 12.9-inch) 
  {}
  @media (max-width: 1280px) // MacBook Pro 13 inch and below 
  {}
  @media (max-width: 1440px) // MacBook Pro 15 inch and below 
  {}
  @media (min-width: 1792px) // MacBook Pro 16 inch and above 
  {}
}
</style>
