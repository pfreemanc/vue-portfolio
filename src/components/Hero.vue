<template>
  <div class="hero">
    <div class="hero__text-container">
      <div class="hero--heading">
        <h1>
          {{ firstName }} <span>{{ lastName }}</span>
        </h1>
        <h2>Front-end web developer</h2>
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

    .hero--heading {
      margin-top: 20px;
    }

    h1 span {
      display: block;
    }

    h1 {
      font-size: clamp(4.2rem, 8vw, 10.2rem);
      margin: 0;
    }

    h2 {
      // font-size: 3.6rem;
      margin: 0;
      font-size: clamp(1.6rem, 5vw, 4.2rem);
      font-weight: 300;
    }
  }

  svg {
    margin-top: -1px;
  }
}

@media (max-width: 320px) // Mobile small (iPhone SE original) and below [very rare now] 
    {}
    @media (max-width: 375px) // Mobile (iPhone Regular) and below 
    {}
    @media (max-width: 414px) // Mobile large (iPhone Max) and below 
    {}
    @media (max-width: 768px) // Tablet and below (most iPads) 
    {
      // .hero__text-container {

      //   h1 {
      //     font-size: 6rem;
      //   }
      //   h1 span{
      //     font-size: 4.8rem;
      //   }
      // }
    }
    @media (max-width: 1024px) // Tablet Large and below (iPad Pro 12.9-inch) 
    {}
    @media (max-width: 1280px) // MacBook Pro 13 inch and below 
    {}
    @media (max-width: 1440px) // MacBook Pro 15 inch and below 
    {}
    @media (min-width: 1792px) // MacBook Pro 16 inch and above 
    {}
</style>
