<template>
  <div class="hero">
    <div class="hero__wrapper wrapper">
      <div class="hero__text-container">
        <div class="hero--heading">
          <h1>
            {{ firstName }} <span>{{ lastName }}</span>
          </h1>
          <h2>Front-end web developer</h2>
        </div>
      </div>
    </div>
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
</template>

<script>
import db from "../../db.json"

export default {
  data() {
    return {
      firstName: db.personalInfo.firstName,
      lastName: db.personalInfo.lastName,
    }
  },
  async created() {
    console.log(db)
  },
}
</script>

<style lang="scss">
@import "../styles/config.scss";

.hero {
  background-color: black;
  // margin-bottom: 100px;

  &__text-container {
    display: flex;
    height: 80vh;
    flex-flow: column nowrap;
    font-family: $secondary-font;
    justify-content: center;
    align-items: center;
    color: white;
    text-align: left;
    // padding: 0 10%;

    .hero--heading {
      margin-top: 20px;
    }

    h1 span {
      display: block;
      font-size: clamp(2.8rem, 8vw, 9.6rem);
    }

    h1 {
      font-size: clamp(3.8rem, 8vw, 9.6rem);
      margin: 0;
      font-weight: 500;
      text-shadow: 3px 5px rgb(119, 77, 153);
    }

    h2 {
      margin: 0;
      font-size: clamp(1.6rem, 2vw, 4.2rem);
      font-weight: 300;
      text-transform: lowercase;
      margin-left: 1px;
    }
  }

  // svg {
  //   margin-top: -5px;
  // }
}
</style>
