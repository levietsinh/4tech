<template>
  <main class="home">
    <HeaderVue />
    <Greeting />
    <AboutUs />
    <Games />
    <Partners />
    <FooterVue />
    <img
      src="~/assets/images/arrow-circle-up.png"
      class="home-arrow"
      :class="{ 'home-arrow-reverse': scrollY > 0 }"
      @click="handleScrollButton"
    />
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
  data() {
    return {
      scrollY: 0,
      footerEl: "",
    }
  },
  mounted() {
    // eslint-disable-next-line nuxt/no-globals-in-created
    window.addEventListener('scroll', this.handleScroll)
    this.$nextTick(() => {
      this.footerEl = document.querySelector(".footer");
    })
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScrollButton() {
      if(this.scrollY > 0) {
        window.scrollTo({
          top: 0,
          behavior: "smooth"
        });
      } else {
        this.footerEl.scrollIntoView({behavior: 'smooth'})
      }
    },
    handleScroll() {
      this.scrollY = window.scrollY
    },
  },
}
</script>
<style lang="scss" scoped>
@import './Home.scss';
</style>
