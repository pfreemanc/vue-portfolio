<template>
  <div class="hero">
    <div class="hero__text-container">
      <h1>
        {{ firstName }} <span>{{ lastName }}</span>
      </h1>
      <h2>Front-end web developer</h2>
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
      firstName: db.personalInfo.firstName,
      lastName: db.personalInfo.lastName
    };
  },
  async created() {
    console.log(db);
  }
};
</script>

<style lang="scss">
@import "../styles/config.scss";

.hero {
  background-color: black;
  height: 80vh;
  margin-bottom: 100px;

  &__text-container {
    height: 80vh;
    display: flex;
    flex-flow: column nowrap;
    font-family: $secondary-font;
    justify-content: center;
    align-items: center;
    color: white;
    text-align: left;
    padding: 0 10%;

    h1 span {
      display: block;
      width: 100%;
    }

    h1 {
      font-size: 7.2rem;
      width: 75%;
    }

    h2 {
      font-size: 3.6rem;
      width: 75%;
      font-weight: 300;
    }
  }

  svg {
    margin-top: -1px;
  }
}
</style>
