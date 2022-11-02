<template>
  <div class="greeting">
    <img src="~/assets/images/fairy-man.png" class="greeting-fairy" />
    <div class="greeting-content">
      <h2 class="greeting-headline">{{ $t('greeting.headline') }}</h2>
      <div class="greeting-countdown d-flex">
        <div class="greeting-countdown__item">
          <p class="countdown-value">
            {{ days }}
          </p>
          <span class="countdown-time">{{ $t('greeting.days') }}</span>
        </div>
        <div class="greeting-countdown__item countdown-value">:</div>
        <div class="greeting-countdown__item">
          <p class="countdown-value">{{ hours }}</p>
          <span class="countdown-time">{{ $t('greeting.hours') }}</span>
        </div>
        <div class="greeting-countdown__item countdown-value">:</div>
        <div class="greeting-countdown__item">
          <p class="countdown-value">{{ minutes }}</p>
          <span class="countdown-time">{{ $t('greeting.minutes') }}</span>
        </div>
        <div class="greeting-countdown__item countdown-value">:</div>
        <div class="greeting-countdown__item">
          <p class="countdown-value">
            {{ seconds }}
          </p>
          <span class="countdown-time">{{ $t('greeting.seconds') }}</span>
        </div>
      </div>
      <p class="greeting-sub">{{ $t('greeting.subText') }}</p>
      <div class="greeting-email">
        <input type="text" :placeholder="$t('greeting.emailPlaceHolder')" />
        <img src="~/assets/images/arrow-right.svg" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GreetingComponent',
  data() {
    return {
      countDownDate: new Date('Jan 1, 2023 00:00:00').getTime(),
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
    }
  },
  mounted() {
    const counter = setInterval(() => {
      const now = new Date().getTime()
      const distance = this.countDownDate - now
      this.days = Math.floor(distance / (1000 * 60 * 60 * 24))
      this.hours = Math.floor(
        (distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
      )
      this.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60))
      this.seconds = Math.floor((distance % (1000 * 60)) / 1000)
      if (distance < 0) {
        clearInterval(counter)
      }
    }, 1000)
  },
}
</script>

<style lang="scss" scoped>
@import './Greeting.scss';
</style>
