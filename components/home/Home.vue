<template>
  <main>
    <HeaderVue />
    <Greeting />
    <AboutUs />
    <Games />
    <Partners />
    <FooterVue />
  </main>
</template>

<script>
import HeaderVue from '../partials/header/Header.vue'
import FooterVue from '../partials/footer/Footer.vue'
import Games from '../games/Games.vue'
import Partners from '../partners/Partners.vue'
import Greeting from './../greeting/Greeting.vue'
import AboutUs from './../about-us/AboutUs.vue'

export default {
  name: 'HomeComponent',
  components: {
    HeaderVue,
    Greeting,
    AboutUs,
    Games,
    Partners,
    FooterVue,
  },
}
</script>
<style lang="scss" scoped>
@import './Home.scss';
</style>
