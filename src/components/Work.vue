<template>
  <section id="work">
    <app-card v-for="(card, index) in work.cards" 
      :key="index"
      :card="card"
      :readMore="work.readMore">
      </app-card>
  </section>
</template>

<script>

import Card from './WorkCard.vue';

export default {
  components: {
    appCard: Card
  },
  props: ['work']
}
</script>

<style scoped lang="scss">
  section {
    margin: 1.5em 18px;
    display: flex;
    justify-content: space-around;
    flex-direction: column;
  }

  @media screen and (min-width: 321px) {
    section {
      flex-wrap: wrap;
      flex-direction: row;
    }
  }
</style>
