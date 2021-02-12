<template>
  <div class="hero">
    <div class="hero__text-container">
      <h1>{{firstName}} <span>{{ lastName }}</span></h1>
      <h2>Front-end web developer</h2>
    </div>
  </div>
</template>

<script>
import database from '../../db.json'

export default {
  data() {
    return {
      firstName: 'Paige',
      lastName: '',
      data: database.personalInfo,
    }
  },
  async created() {
    this.firstName = this.data.name.firstName
    this.lastName = this.data.name.lastName
  }
}
</script>

<style lang="scss" scoped>
  .hero {
    height: 100vh;

    &__text-container {
      height: 100vh;
      display: flex;
      flex-flow: column nowrap;
      justify-content: center;
      align-items: center;
    }
  }
</style>
