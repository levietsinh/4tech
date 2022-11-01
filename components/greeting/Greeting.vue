<template>
  <div class="greeting">
    <img src="~/assets/images/fairy-man.png" class="greeting-fairy" />
    <div class="greeting-content">
      <h2 class="greeting-headline">{{ $t('greeting.headline') }}</h2>
      <div class="greeting-countdown"></div>
      <p>{{ $t('greeting.subText') }}</p>
      <div class="greeting-email">
        <input type="text" :placeholder="$t('greeting.emailPlaceHoder')" />
        <img src="~/assets/images/arrow-right.svg" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GreetingComponent',
}
</script>

<style lang="scss" scoped>
@import './Greeting.scss';
</style>
