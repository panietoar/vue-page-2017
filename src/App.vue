<template>
  <div id="app">
    <app-header :content="content.navigation"></app-header>
    <app-main-heading :content="content.heading"></app-main-heading>
    <app-carousel :slides="content.carousel.slides"></app-carousel>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import MainHeading from './components/MainHeading.vue';
  import Carousel from './components/Carousel.vue';

  export default {
    components: {
      appHeader: Header,
      appMainHeading: MainHeading,
      appCarousel: Carousel
    },
    data() {
      return {
        content: {
          navigation: {
            about: 'about',
            work: 'work',
            contact: 'contact'
          },
          heading: 'We design, produce and deliver brand content.',
          carousel: {
            slides: [{
              image: 'carrusel-1.jpg',
              text: 'We design, produce and deliver brand content.'
            }, {
              image: 'carrusel-2.jpg',
              text: 'Using the best talent, processes and tools.'
            }, {
              image: 'carrusel-3.jpg',
              text: 'The result? Seamless global execution of multiple content types across all markets, without compromising creative quality.'
            }, {
              image: 'carrusel-4.jpg',
              text: 'We call this brand logistics™, our new vision for a new content-driven media landscape.'
            }]
          }
        }
      }
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