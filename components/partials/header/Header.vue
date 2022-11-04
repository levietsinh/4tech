<template>
  <b-navbar class="header" toggleable="lg" type="dark" variant="info">
    <b-navbar-brand href="#">
      <img
        class="header-logo"
        src="~/assets/images/4tech-logo.svg"
        alt="4Tech"
      />
    </b-navbar-brand>
    <b-navbar-toggle target="nav-collapse" @click="showMenu = true">
      <img src="~/assets/images/menu.png" />
    </b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <div v-if="isMobile" class="header-close">
        <b-nav-item class="header-lang__mobile">
          <b-nav-item-dropdown class="header-lang__dropdown" left no-caret>
            <template #button-content>
              <span class="d-flex">
                <img
                  :src="
                    require(`@/assets/images/${
                      currentLang === 'en' ? 'united-states' : 'vietnam'
                    }.svg`)
                  " />
                <img class="ml-2" src="~/assets/images/arrow-down-black.svg"
              /></span>
            </template>
            <b-dropdown-item
              v-for="flag in flags"
              :key="flag.key"
              @click="showMenu = false"
            >
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
        <b-navbar-toggle target="nav-collapse" @click="showMenu = false">
          <img src="~/assets/images/close.png" />
        </b-navbar-toggle>
      </div>
      <b-navbar-nav v-if="isMobile" class="ml-auto header-nav">
        <b-nav-item @click="scrollToView('aboutEl')">
          <b-navbar-toggle target="nav-collapse">
            {{ $t('header.aboutUs') }}
          </b-navbar-toggle>
        </b-nav-item>
        <b-nav-item @click="scrollToView('gamesEl')">
          <b-navbar-toggle target="nav-collapse">
            {{ $t('header.games') }}
          </b-navbar-toggle>
        </b-nav-item>
        <b-nav-item @click="scrollToView('partnersEl')">
          <b-navbar-toggle target="nav-collapse">
            {{ $t('header.partner') }}
          </b-navbar-toggle>
        </b-nav-item>
        <b-nav-item @click="scrollToView('footerEl')">
          <b-navbar-toggle target="nav-collapse">
            {{ $t('header.contactUs') }}
          </b-navbar-toggle>
        </b-nav-item>
      </b-navbar-nav>
      <b-navbar-nav v-else class="ml-auto header-nav">
        <b-nav-item @click="scrollToView('aboutEl')">
          {{ $t('header.aboutUs') }}
        </b-nav-item>
        <b-nav-item @click="scrollToView('gamesEl')">
          {{ $t('header.games') }}
        </b-nav-item>
        <b-nav-item @click="scrollToView('partnersEl')">
          {{ $t('header.partner') }}
        </b-nav-item>
        <b-nav-item @click="scrollToView('footerEl')">
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
      isMobile: false,
      showMenu: false,
      footerEl: '',
      aboutEl: '',
      gamesEl: '',
      partnersEl: '',
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
  watch: {
    showMenu: {
      handler(value) {
        document.body.style.overflow = value ? 'hidden' : ''
      },
    },
  },
  mounted() {
    this.$nextTick(() => {
      this.onResize()
      window.addEventListener('resize', this.onResize)
      this.aboutEl = document.querySelector('.about')
      this.footerEl = document.querySelector('.footer-copyright')
      this.gamesEl = document.querySelector('.games')
      this.partnersEl = document.querySelector('.partners')
    })
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.onResize)
  },
  methods: {
    onResize() {
      this.isMobile = window.innerWidth < 821
    },
    scrollToView(element) {
      this.showMenu = false
      this[element].scrollIntoView({ behavior: 'smooth' })
    },
  },
}
</script>

<style lang="scss" scoped>
@import './Header.scss';
</style>
