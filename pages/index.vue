<template>
  <div id="home">
    <section id="hero">
      <hero />
    </section>
    <section id="program">
      <program />
    </section>
    <section id="booking">
      <booking />
    </section>
    <section id="footer"><Footer /></section>
  </div>
</template>

<style scoped>
.testkort {
  background-color: palegoldenrod;
}
#hero {
  min-height: 100vh;
  /*background-image: '~/assets/background.jpg' */;
}
#booking {
  min-height: 50vh;
  background-color: 'white';
}
#blaj {
  min-height: 20vh;
  background-color: #689689;
}

#home {
  position: relative;
}

#program {
  min-height: 30vh;
  background-color: #1A1F28;
}
</style>

<script>
import hero from '~/pages/hero'
import booking from '~/pages/booking'
import footer from '~/components/Footer'
import program from '~/pages/program'

export default {
  components: {
    hero,
    booking,
    footer,
    program
  },
  data() {
    return {
      background: require('~/assets/test.JPG'),
    }
  },
}
</script>
