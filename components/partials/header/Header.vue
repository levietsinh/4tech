<template>
  <b-navbar class="header" toggleable="lg" type="dark" variant="info">
    <b-navbar-brand href="#">
      <img
        class="header-logo"
        src="~/assets/images/4tech-logo.svg"
        alt="4Tech"
      />
    </b-navbar-brand>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav class="ml-auto header-nav">
        <b-nav-item href="#">
          {{ $t('header.aboutUs') }}
        </b-nav-item>
        <b-nav-item href="#">
          {{ $t('header.games') }}
        </b-nav-item>
        <b-nav-item href="#">
          {{ $t('header.partner') }}
        </b-nav-item>
        <b-nav-item href="#">
          {{ $t('header.contactUs') }}
        </b-nav-item>
        <b-nav-item class="header-lang">
          <b-nav-item-dropdown class="header-lang__dropdown" right no-caret>
            <template #button-content>
              <span class="d-flex">
                <img
                  :src="
                    require(`@/assets/images/${
                      currentLang === 'en' ? 'united-states' : 'vietnam'
                    }.svg`)
                  " />
                <img class="ml-2" src="~/assets/images/arrow-down.svg"
              /></span>
            </template>
            <b-dropdown-item v-for="flag in flags" :key="flag.key">
              <nuxt-link :to="switchLocalePath(flag.key)">
                <span class="header-lang__tick"
                  ><img
                    v-show="currentLang === flag.key"
                    src="~/assets/images/tick.svg"
                /></span>

                <img :src="require(`@/assets/images/${flag.image}.svg`)" />
                <span>{{ flag.value }}</span>
              </nuxt-link>
            </b-dropdown-item>
          </b-nav-item-dropdown>
        </b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<script>
export default {
  name: 'HeaderComponent',
  data() {
    return {
      currentLang: this.$i18n.locale,
      flags: [
        {
          key: 'vi',
          image: 'vietnam',
          value: 'Tiếng Việt',
        },
        {
          key: 'en',
          image: 'united-states',
          value: 'English',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
@import './Header.scss';
</style>
