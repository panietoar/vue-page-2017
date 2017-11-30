<template>
  <article v-if="isColored" class="colorCard" :class="card.color">
    <header>
      <h3> {{ card.title }} </h3>
      <h2> {{ card.subtitle }} </h2>
    </header>
    <div class="content">
      {{ card.text }}
    </div>
    <footer>
      <a href="#">
        {{ readMore }}
      </a>
    </footer>
  </article>

  <article class="image" :class="card.image.position" v-else>
    <img :src="imagePath" >
    <div class="content">
      <h3> {{ card.title }} </h3>
        {{ card.text }}
    </div>
  </article>
</template>

<script>
export default {
  props: ['card', 'readMore'],
  computed: {
    isColored() {
      return this.card.color;
    },
    imagePath() {
       return '/src/assets/Images/' + this.card.image.path;
    }
  }
}
</script>

<style scoped lang="scss"> 
  article {
    box-shadow: 0 2px 2px rgba(0, 0, 0, .38);
    margin-bottom: .5em; 
    position: relative;

    a {
      text-decoration: none;
      color: #FFF;
    }

    &.image {
    padding: 140px 25px;
      
      .content {
        font-size: 16px;
        position: absolute;
        width: 80%;
      
        h3 {
          font-family: 'Montserrat', sans-serif;
          text-transform: uppercase;
          font-size: 12px;
          margin-bottom: 6px;
          font-weight: bold;
        }
      }

      img {
        position: absolute;
        left: 0;
        width: 100%;
      }

      &.top {
        img {
          top: 0;
        }

        .content {
          top: 60%;
        }
      }

      &.bottom {
        img {
          bottom: 0;
        }
        
        .content {
          top: 5%;
        }
      }
    }

    &.colorCard {
      color: #FFF;
      transition: background-color, color 0.5s;
      padding: 2em 25px;

      header {

        h3, h2{
          font-size: 8px;
        }

        h3 {
          border-bottom: 1px solid #fff;
          text-transform: uppercase;
          margin-bottom: .5em;
          padding-bottom: .5em;
        }

      }
    
      footer {
        border-top: 1px solid #fff;
         a {
           text-transform: uppercase;
           font-size: 8px;
         }
      }

      .content {
        font-size: 16px;
        line-height: 1;
        margin: 3em 0;
      }

      &:hover {
        color: #000;
        background-color: #FFF !important;

        a {
          color: #000;
        }

        h3 {
          border-bottom: 1px solid #000;
        }

        footer {
          border-top: 1px solid #000;
        }

      }

      &.blue{
        background-color: #2828ff;
      }
      &.red{
        background-color: #ff0000;
      }
      &.black {
        background-color: #000000;
      }
    }
  }

      
  @media screen and (min-width: 321px) {
    article {
      width: 30%;
      margin-bottom: .5em; 

      &.image {
      padding: 50% 80px;
        
        .content {
          font-size: 16px;
          width: 80%;
        
          h3 {
            font-size: 12px;
            margin-bottom: 6px;
          }
        }

        &.top {
          img {
            top: 0;
          }

          .content {
            top: 70%;
          }
        }

        &.bottom {
          img {
            bottom: 0;
          }
          
          .content {
            top: 15%;
          }
        }
      }

      &.colorCard {
        padding: 2em 80px;

        header {

          h3, h2{
            font-size: 12px;
          }

          h3 {
            margin-bottom: .5em;
            padding-bottom: .5em;
          }

        }

        footer {
          a {
            font-size: 12px;
          }
        }
      
        .content {
          font-size: 36px;
          line-height: 1;
          margin: 3em 0;
        }
      }
    }
  }
</style>
