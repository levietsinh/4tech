<template>
  <footer class="footer">
    <b-container>
      <b-row>
        <b-col cols="12" md="4" class="footer-col px-3">
          <div class="footer-logo">
            <img src="~/assets/images/4tech-logo.svg" alt="4tech" />
          </div>
          <div class="footer-social">
            <img src="~/assets/images/twitter.svg" />
            <img src="~/assets/images/facebook.svg" />
            <img src="~/assets/images/linked.svg" />
          </div>
        </b-col>
        <b-col cols="12" md="4" class="footer-col footer-contact px-3">
          <h3 class="footer-title">{{ $t('footer.address.title') }}</h3>
          <div class="footer-address d-flex">
            <span><img src="~/assets/images/address.svg" /></span>
            <div class="footer-text">
              <p class="mb-3">{{ $t('footer.address.addressUS') }}</p>
              <p>{{ $t('footer.address.addressVN') }}</p>
            </div>
          </div>
          <div class="footer-address d-flex">
            <span><img src="~/assets/images/phone.svg" /></span>
            <div class="footer-text footer-phone">
              <p>{{ $t('footer.address.phoneNumber') }}</p>
            </div>
          </div>
          <div class="footer-address"></div>
        </b-col>
        <b-col cols="12" md="4" class="footer-col px-3">
          <h3 class="footer-title">{{ $t('footer.subscribe.title') }}</h3>
          <div class="footer-subscribe">
            <p class="footer-text">{{ $t('footer.subscribe.text') }}</p>
            <div class="footer-email mt-2">
              <input
                type="text"
                :placeholder="$t('greeting.emailPlaceHolder')"
              />
              <img src="~/assets/images/arrow-right-white.svg" />
            </div>
          </div>
        </b-col>
      </b-row>
    </b-container>
    <div class="footer-copyright">
      {{ $t('footer.copyright') }}
    </div>
  </footer>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import './Footer.scss';
</style>