<template>
  <b-container class="games" fluid>
    <b-row>
      <b-col cols="12" class="games-header">
        <h2>{{ $t('games.title') }}</h2>
        <p>{{ $t('games.des') }}</p>
      </b-col>
    </b-row>
    <b-row class="games-list">
      <b-col
        cols="6"
        md="3"
        order="1"
        order-md="1"
        align-self="start"
        class="games-header"
      >
        <div v-for="game in games.slice(0, 3)" :key="game.image">
          <img :src="require(`@/assets/images/${game.image}.png`)" />
        </div>
      </b-col>
      <b-col
        cols="6"
        md="3"
        order="3"
        order-md="2"
        align-self="end"
        class="games-header"
      >
        <div v-for="game in games.slice(3, 6)" :key="game.image">
          <img :src="require(`@/assets/images/${game.image}.png`)" /></div
      ></b-col>
      <b-col
        cols="6"
        md="3"
        order="2"
        order-md="3"
        align-self="start"
        class="games-header"
      >
        <div v-for="game in games.slice(6, 9)" :key="game.image">
          <img :src="require(`@/assets/images/${game.image}.png`)" /></div
      ></b-col>
      <b-col
        cols="6"
        md="3"
        order="4"
        order-md="4"
        align-self="end"
        class="games-header"
      >
        <div v-for="game in games.slice(-3)" :key="game.image">
          <img :src="require(`@/assets/images/${game.image}.png`)" /></div
      ></b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: 'GamesComponent',
  data() {
    return {
      games: [
        {
          title: this.$t('game1.title'),
          des: this.$t('game1.des'),
          image: 'game-1',
        },
        {
          title: this.$t('game2.title'),
          des: this.$t('game2.des'),
          image: 'game-2',
        },
        {
          title: this.$t('game3.title'),
          des: this.$t('game3.des'),
          image: 'game-3',
        },
        {
          title: this.$t('game4.title'),
          des: this.$t('game4.des'),
          image: 'game-4',
        },
        {
          title: this.$t('game5.title'),
          des: this.$t('game5.des'),
          image: 'game-5',
        },
        {
          title: this.$t('game6.title'),
          des: this.$t('game6.des'),
          image: 'game-6',
        },
        {
          title: this.$t('game7.title'),
          des: this.$t('game7.des'),
          image: 'game-7',
        },
        {
          title: this.$t('game8.title'),
          des: this.$t('game8.des'),
          image: 'game-8',
        },
        {
          title: this.$t('game9.title'),
          des: this.$t('game9.des'),
          image: 'game-9',
        },
        {
          title: this.$t('game10.title'),
          des: this.$t('game10.des'),
          image: 'game-10',
        },
        {
          title: this.$t('game11.title'),
          des: this.$t('game11.des'),
          image: 'game-11',
        },
        {
          title: this.$t('game12.title'),
          des: this.$t('game12.des'),
          image: 'game-12',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
@import './Games.scss';
</style>