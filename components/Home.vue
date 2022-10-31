<template>
  <main>
    <Header />
    <!-- <h1>{{ $t('welcome') + $i18n.locale }}</h1>

    <nuxt-link v-if="$i18n.locale !== 'en'" :to="switchLocalePath('en')">
      English
    </nuxt-link>

    <nuxt-link v-if="$i18n.locale !== 'vi'" :to="switchLocalePath('vi')">
      Tiếng Việt
    </nuxt-link> -->
  </main>
</template>

<script>
import Header from './partials/header/Header.vue'
export default {
  name: 'HomeComponent',
  components: {
    Header,
  },
}
</script>
