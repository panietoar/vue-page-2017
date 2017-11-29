<template>
  <section>
    <div class="content">
      <div class="title">{{ hero.title }}</div>
      <div class="text">{{ hero.text }}</div>
      <div class="secondary">{{ hero.secondaryText }}</div>
      <a class="more" href="#">{{ hero.learnMore }}</a>
    </div>
  </section>
</template>

<script>
  export default {
    props: ['hero']
  }
</script>

<style scoped lang="scss">

  section {
    width: 100%;
    height: 100%;
    background: linear-gradient( rgba(4, 4, 4, .2), rgba(4, 4, 4, .2)), url('../assets/Images/brothers.jpg');
    background-size: 250% 100%;
    background-position: 50% 0;
    position: relative;
    color: #FFF;

    .content {
      position: absolute;
      top: 30%;
      left: 20px;
      margin: 1em 0;
      width: 50%;

      &>div {
        margin-bottom: 20px;
      }
      
      a {
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

      .title,
      .secondary {
        text-transform: uppercase;
        font-size: 12px;
        font-family: 'Montserrat', sans-serif;
        font-weight: bold;
      }

      .text {
        font-size: 16px;
      }
    }
  }
  
  @media screen and (min-width: 321px) {
    section {
      background-size: 150% 100%;
      background-position: 50% 0;
      
      .content {
        left: 60%;
        width: 30%;
      
        .title {
          font-size: 18px;
        }
      
        .secondary {
          font-size: 16px;
          font-family: 'Roboto', sans-serif;
        }
      
        .text {
          font-size: 36px;
        }
      }
    }
  }
</style>