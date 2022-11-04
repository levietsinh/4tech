<template>
  <div class="partners">
    <h2 class="partners-title">{{ $t('partners.title') }}</h2>
    <div class="partners-carousel">
      <VueSlickCarousel v-bind="settings">
        <template #nextArrow>
          <div class="custom-arrow">
            <img src="@/assets/images/arrow-right.png" />
          </div>
        </template>
        <div v-for="partner of 7" :key="partner">
          <img :src="require(`@/assets/images/partner-${partner}.png`)" />
        </div>
        <template #prevArrow>
          <div class="custom-arrow">
            <img src="@/assets/images/arrow-left.png" />
          </div>
        </template>
      </VueSlickCarousel>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'

export default {
  name: 'PartnersComponent',
  components: {
    VueSlickCarousel,
  },
  data() {
    return {
      windowWidth: 0,
      settings: {
        autoplay: true,
        autoplaySpeed: 2500,
        arrows: true,
        infinite: true,
        speed: 500,
        slidesToShow: 5,
      },
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.onResize()
      window.addEventListener('resize', this.onResize)
    })
  },

  beforeDestroy() {
    window.removeEventListener('resize', this.onResize)
  },
  methods: {
    onResize() {
      this.windowWidth = window.innerWidth
      this.settings = {
        ...this.settings,
        slidesToShow: this.windowWidth < 821 ? 3 : 5,
      }
    },
  },
}
</script>

<style lang="scss" scoped>
@import './Partners.scss';
</style>
