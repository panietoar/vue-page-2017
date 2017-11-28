<template>
  <section class="gallery">
    <img :src="backgroundImage" alt="">
      <h2>{{ currentSlide.text }}</h2>
      <a class="more" href="#">More about Us</a>
      <div class="controls">
        <div v-for="(slide, index) in slides" :key="slide.text" class="slide-control" :class="{active: isSlideActive(index)}" @click.prevent="selectSlide(index)"></div>
      </div>
  </section>
</template>

<script>
  export default {
    data() {
      return {
        currentSlideIndex: 0
      }
    },
    props: ['slides'],
    computed: {
      currentSlide() {
        return this.slides[this.currentSlideIndex];
      },
      backgroundImage() {
        return '/src/assets/Images/' + this.currentSlide.image;
      }
    },
    methods: {
      isSlideActive(index) {
        return index === this.currentSlideIndex;
      },
      selectSlide(index) {
        this.currentSlideIndex = index;
      }
    }
  }
</script>

<style scoped lang="scss">
  section {
    width: 100%;
    height: 70%;
    overflow: hidden;
    position: relative;
    color: #FFF;
    display: flex;
    background-image: linear-gradient(to right, black, black 50%, rgba(0, 0, 0, 0));
    img {
      opacity: 0.3;
    }
    h2,
    a.more,
    .controls {
      position: absolute;
      left: 20px;
    }
    h2 {
      top: 5em;
      font-size: 16px;
      font-weight: 300;
      width: 90%;
    }
    a.more {
      font-size: 16px;
      color: #fff;
      text-decoration: none;
      bottom: 120px;
      &::after {
        background-image: url("/src/assets/asset_icon/arrow-white@3x.png");
        background-size: 30px 20px;
        width: 30px;
        content: "";
        height: 20px;
        display: inline-block;
        margin-left: 20px;
        vertical-align: middle;
      }
    }
    .controls {
      width: 60%;
      height: 20px;
      bottom: 80px;
      display: flex;
      justify-content: space-between;
      .slide-control {
        width: 40px;
        height: 20px;
        border-bottom: 1px solid #fff;
        cursor: pointer;
        &.active {
          border-bottom: 5px solid #fff;
        }
      }
    }
  }
  
  @media screen and (min-width: 321px) {
    section {
      height: 50%;
      h2,
      a.more,
      .controls {
        left: 200px;
      }
      h2 {
        top: 1em;
        font-size: 36px;
        font-weight: 300;
        width: 60%;
      }
      .controls {
        width: 40%;
      }
    }
  }
</style>