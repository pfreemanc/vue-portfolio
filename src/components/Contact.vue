<template>
  <div class="contact">
    <div class="wrapper">
      <h2 class="contact--heading section--heading">Contact</h2>

      <ul class="contact__list">
        <li
          class="contact__list--item"
          v-for="(contact, index) in contact"
          :key="index"
        >
          <font-awesome-icon :icon="['fab', 'twitter']" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import DB from '../../db.json'

export default {
  data() {
    return {
      contact: [],
    }
  },
  async created() {
    this.contact = await DB.personalInfo.contact
  },
}
</script>

<style lang="scss">
.contact {
  &--heading {
    text-align: center;
  }

  &__list {
    max-width: 80%;
    margin: 0 auto;
  }
}
</style>
