<template>
    <div class="hero-content">

      <v-container class="video-container pa-0">
        <video id="video-background" :poster="poster" autoplay preload="metadata" muted loop>
          <source :src="video" type="video/mp4" />
        </video>
      </v-container>

      <v-container id="on-top" cols="12" class="relative" nogutters>
        <v-container fluid class="logo-holder">
          <logo textColor="#ffffff"/>
        </v-container>
        <v-container class="button-holder">
            <book-button-vue/>
        </v-container>
    </v-container>
    </div>
</template>

<style scoped>

.hero-content {
  display: -webkit-box;
  align-content: center;
  justify-content: center;
  min-height: 100vh;
  min-width: 100vw;
  position: absolute;
  top: 0;
  left: 0;
  align-items: center;
  overflow-x: hidden;
}

.video-container {
  position: absolute;
  width: 100vw;
}

h1 {
  font-size: 3em;
}

.logo-holder {
  align-items: center;
  justify-content: center;
  display: flex;
}
.button-holder {
  align-items: center;
  justify-content: center;
  display: flex;
}

#video-background {
  right: 0;
  bottom: 0;
  min-width: 100vw;
  min-height: 100vh;
  opacity: 1;
  filter: brightness(70%);
  /*background: url('~assets/img/firstframe.jpg') 50% 50% / cover */;
}

#on-top {
  padding-top: 20vh;
  z-index: 1;
}

</style>

<script>
import BookButtonVue from '../components/BookButton.vue'
import Logo from '../components/Logo.vue'

export default {
  components: {
    BookButtonVue,
    Logo,
  },
  data() {
    return {
      background: require('~/assets/test3.jpg'),
      logo: require('~/assets/logo.svg'),
      video: require('~/assets/stuga_short.mp4'),
      poster: require('~/assets/forest.jpg'),

      viewheight: window.innerHeight,
    }
  },
}
</script>
