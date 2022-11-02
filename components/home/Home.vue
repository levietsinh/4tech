<template>
  <main>
    <Header />
    <Greeting />
    <AboutUs />
    <Games />
  </main>
</template>

<script>
import Header from '../partials/header/Header.vue'
import Games from '../games/Games.vue'
import Greeting from './../greeting/Greeting.vue'
import AboutUs from './../about-us/AboutUs.vue'

export default {
  name: 'HomeComponent',
  components: {
    Header,
    Greeting,
    AboutUs,
    Games,
  },
}
</script>
<style lang="scss" scoped>
@import './Home.scss';
</style>
