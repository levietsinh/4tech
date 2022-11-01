<template>
  <main>
    <Header />
    <Greeting/>
  </main>
</template>

<script>
import Header from '../partials/header/Header.vue'
import Greeting from "./../greeting/Greeting.vue"
export default {
  name: 'HomeComponent',
  components: {
    Header,
    Greeting
  },
}
</script>
<style lang="scss" scoped>
@import "./Home.scss";
</style>
