<template>
  <div class="partners">
    <h2 class="partners-title">{{ $t('partners.title') }}</h2>
    <div class="partners-carousel">
      <VueSlickCarousel v-bind="settings">
        <div>1</div>
        <div>2</div>
        <div>3</div>
        <div>4</div>
      </VueSlickCarousel>
    </div>
  </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
// optional style for arrows & dots
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
export default {
  name: 'PartnersComponent',
  components: {
    VueSlickCarousel,
  },
  data() {
    return {
      settings: {
        centerMode: true,
        centerPadding: '20px',
        focusOnSelect: true,
        infinite: true,
        slidesToShow: 3,
        speed: 500,
      },
    }
  },
}
</script>

<style lang="scss" scoped>
@import './Partners.scss';
</style>
