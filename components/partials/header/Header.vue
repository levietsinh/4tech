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
      <!-- Right aligned nav items -->
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
        <b-nav-item>
            <img src="~/assets/images/vietnam.svg">
          <b-nav-item-dropdown class="header-lang" right>
            <b-dropdown-item>
              <nuxt-link :to="switchLocalePath('vi')">
                <img src="~/assets/images/vietnam.svg" />
                <span>Tiếng Việt</span>
              </nuxt-link>
            </b-dropdown-item>
            <b-dropdown-item>
              <nuxt-link :to="switchLocalePath('en')">
                <img src="~/assets/images/united-states.svg" />
                <span>English</span>
              </nuxt-link>
            </b-dropdown-item>
          </b-nav-item-dropdown>
        </b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import './Header.scss';
</style>
