<template>
  <footer>
    <div class="information">
      <div class="logo">
        <img src="../assets/asset_icon/Logo-Prodigious-White@3x.png" alt="Prodigious Logo" width="170">
      </div>
      <div class="summary">
        {{ footer.summary }}
      </div>
      <div class="social">
        <a v-for="socialLink in footer.social" :key="socialLink.alt" :href="socialLink.url">
          <img :src="'/src/assets/asset_icon/' + socialLink.image" :alt="socialLink.alt" height="20">
        </a>
      </div>
    </div>
    <div class="links">
      <a class="cta" href="#contact"> {{ footer.contactCta }} </a>
      <nav>
        <a v-for="link in footer.footerLinks" :href="link.url">{{ link.label }}</a>
      </nav>
      <p class="copyright"> {{ footer.copyright }} </p>
    </div>
  </footer>
</template>

<script>
  export default {
    props:['footer']
  }

</script>

<style scoped lang="scss">
  footer {
    font-family: 'Montserrat', sans-serif;
    font-weight: thin;
    font-size: 12px;
    padding: 20px 18px;
    background-color: #000000;
    color: #FFFFFF;

    a {
      color: #FFFFFF;
      text-decoration: none;
    }

    .summary {
      font-size: 14px;
      margin-bottom: 24px;
    }

    .social {
      display: flex;
      justify-content: space-between;
      margin-bottom: 40px;
    }

    .links {

      a.cta {
        width: 100%;
        border: 1px solid #FFF;
        text-align: center;
        padding: 15px 40%;
        -webkit-transition: all 0.5s;
        -moz-transition: all 0.5s;
        transition: all 0.5s;

        &:hover {
          background-color: #FFFFFF;
          color: #000000;
        }
      }

      nav {
        margin-top: 32px;
        display: flex;
        flex-wrap: wrap;

        a {
          width: 50%;
          margin-top: 0.5em;
        }
      }

      .copyright {
        margin-top: 24px;
        margin-bottom: 0;
      }
    }
  }

  @media screen and (min-width: 321px) {
    footer {
      margin-top: 48px;
      padding: 100px 120px;
      display: flex;
      flex-flow: row-reverse;
      justify-content: space-around;

      .links {
        width: 25%;
        text-align: right;
        margin-top: 1em;

        a.cta {
          padding: 15px 20%;
        }

        nav {
          flex-direction: column;
          align-items: flex-end;

        }

      }

      .information {
        width: 70%;

        .social {
          width: 60%;
          margin: 0;
        }

      }

    }
  }
</style>