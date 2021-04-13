<template>
    <v-btn
    class="book"
    depressed
    rounded
    x-large
    color="accent"
    @click="sendToBook">
    Boka nu
    </v-btn>
</template>

<style scoped>
  .v-btn {
    font-family: 'Poppins';
    font-weight: 700;
    font-size: 1.2em;
    font-style: normal;
  }
</style>

<script>
export default {
  data() {
    return {
      scrollOptions: {
      duration: 1200,
      offset: 0,
      easing: 'easeInOutCubic',
      },
    }
  },
  methods: {
    sendToBook() {
      this.$vuetify.goTo('#booking', this.scrollOptions)
    },
  },
}
</script>