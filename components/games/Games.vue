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
        v-for="(gameGroup, index) in games"
        :key="index"
        cols="6"
        md="3"
        :order="index === 1 ? 3 : index === 2 ? 2 : index + 1"
        :order-md="index + 1"
        :align-self="index % 2 === 0 ? 'start' : 'end'"
        :class="`games-header games-list-${index + 1}`"
      >
        <div v-for="game in gameGroup" :key="game.image" class="game-item">
          <img :src="require(`@/assets/images/${game.image}.png`)" />
          <div class="games-text text-left">
            <h4>{{ game.title }}</h4>
            <p>{{ game.des }}</p>
          </div>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: 'GamesComponent',
  data() {
    return {
      games: [
        [
          {
            title: this.$t('games.game1.title'),
            des: this.$t('games.game1.des'),
            image: 'game-1',
          },
          {
            title: this.$t('games.game2.title'),
            des: this.$t('games.game2.des'),
            image: 'game-2',
          },
          {
            title: this.$t('games.game3.title'),
            des: this.$t('games.game3.des'),
            image: 'game-3',
          },
        ],
        [
          {
            title: this.$t('games.game4.title'),
            des: this.$t('games.game4.des'),
            image: 'game-4',
          },
          {
            title: this.$t('games.game5.title'),
            des: this.$t('games.game5.des'),
            image: 'game-5',
          },
          {
            title: this.$t('games.game6.title'),
            des: this.$t('games.game6.des'),
            image: 'game-6',
          },
        ],
        [
          {
            title: this.$t('games.game7.title'),
            des: this.$t('games.game7.des'),
            image: 'game-7',
          },
          {
            title: this.$t('games.game8.title'),
            des: this.$t('games.game8.des'),
            image: 'game-8',
          },
          {
            title: this.$t('games.game9.title'),
            des: this.$t('games.game9.des'),
            image: 'game-9',
          },
        ],
        [
          {
            title: this.$t('games.game10.title'),
            des: this.$t('games.game10.des'),
            image: 'game-10',
          },
          {
            title: this.$t('games.game11.title'),
            des: this.$t('games.game11.des'),
            image: 'game-11',
          },
          {
            title: this.$t('games.game12.title'),
            des: this.$t('games.game12.des'),
            image: 'game-12',
          },
        ],
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
@import './Games.scss';
</style>
