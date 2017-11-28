<template>
  <div id="app">
    <app-header v-if="content.navigation" :content="content.navigation" @languageSelected="changeLang"></app-header>
    <app-main-heading v-if="content.heading" :content="content.heading"></app-main-heading>
    <app-carousel v-if="content.carousel" :carousel="content.carousel"></app-carousel>
    <app-hero v-if="content.hero" :hero="content.hero"></app-hero>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import MainHeading from './components/MainHeading.vue';
  import Carousel from './components/Carousel.vue';
  import Hero from './components/Hero.vue';
  import axios from 'axios';

  export default {
    components: {
      appHeader: Header,
      appMainHeading: MainHeading,
      appCarousel: Carousel,
      appHero: Hero
    },
    data() {
      return {
        content: {}
      }
    },
    methods: {
      changeLang(lang) {
        var vm = this;
        axios.get('public/json/content-' + lang + '.json').then(function(response) {
          vm.content = response.data;
        });
      }
    },
    beforeMount() {
      var vm = this;
      axios.get('public/json/content-eng.json').then(function(response) {
        vm.content = response.data;
      });
    }
  }
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Roboto:300');
  html,
  body,
  #app {
    height: 100%;
  }
  
  body {
    font-family: 'Roboto', sans-serif;
  }
</style>