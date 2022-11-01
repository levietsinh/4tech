<template>
  <main>
    <Header />
    <Greeting />
    <AboutUs />
  </main>
</template>

<script>
import Header from '../partials/header/Header.vue'
import Greeting from './../greeting/Greeting.vue'
import AboutUs from './../about-us/AboutUs.vue'
export default {
  name: 'HomeComponent',
  components: {
    Header,
    Greeting,
    AboutUs,
  },
}
</script>
<style lang="scss" scoped>
@import './Home.scss';
</style>
