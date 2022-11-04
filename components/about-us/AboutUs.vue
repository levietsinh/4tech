<template>
  <b-container class="about">
    <b-row class="about-row">
      <b-col cols="12" md="6" class="about-col about-left">
        <h2>{{ $t('aboutUs.title') }}</h2>
        <p>{{ $t('aboutUs.subText') }}</p>
        <div class="about-statistic">
          <div class="about-statistic-type">
            <h3>600M+</h3>
            <h4>{{ $t('aboutUs.users') }}</h4>
          </div>
          <div class="about-statistic-type">
            <h3>135+</h3>
            <h4>{{ $t('aboutUs.games') }}</h4>
          </div>
        </div>
      </b-col>
      <b-col cols="12" md="6" class="about-col about-right">
        <ul>
          <li v-for="service in services" :key="service.img">
            <div class="service-icon">
              <img :src="require(`@/assets/images/${service.img}.svg`)" />
            </div>
            <div class="service-item">
              <span class="service-title">{{ service.title }}</span>
              <span class="service-des">{{ service.des }}</span>
            </div>
          </li>
        </ul>
      </b-col>
    </b-row>
    <b-row class="about-image">
      <b-col cols="12" class="about-image-col">
        <div class="about-image-global">
          <img src="@/assets/images/map.png" />
        </div>
        <img class="about-image-angle" src="@/assets/images/angle.png" />
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: 'AboutUsComponent',
  data() {
    return {
      services: [
        {
          title: this.$t('aboutUs.fullDay.title'),
          des: this.$t('aboutUs.fullDay.des'),
          img: 'full-day',
        },
        {
          title: this.$t('aboutUs.design.title'),
          des: this.$t('aboutUs.design.des'),
          img: 'design',
        },
        {
          title: this.$t('aboutUs.team.title'),
          des: this.$t('aboutUs.team.des'),
          img: 'team',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
@import './AboutUs.scss';
</style>
