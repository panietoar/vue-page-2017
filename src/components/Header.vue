<template>
  <header class="row">
    <div class="logo" >
      <img src="../assets/asset_icon/Logo-Prodigious-Balck@3x.png" alt="Prodigious Logo" width="120">
    </div>
    <i @click="openNav" class="material-icons">menu</i>
    <nav class="four columns">
      <ul>
        <li><a href="#about">{{ content.about }}</a></li>
        <li><a href="#work">{{ content.work }}</a></li>
        <li><a href="#contact">{{ content.contact }}</a></li>
      </ul>
    </nav>
    <select class="four columns" id="language">
      <option v-for="language in languages" :value="language">{{ language }}</option>
    </select>
  </header>
</template>

<script>
  export default {
    data() {
      return {
        languages: [
          'eng',
          'esp'
        ]
      }
    },
    props: ['content'],
    methods: {
      openNav() {
        console.log('aja');
      }
    }
  }
</script>

<style scoped lang="scss">
  header {
    height: 34px;
    box-shadow: 0 4px 4px 0 rgba(0, 0, 0, .38);
    padding: 20px 30px 26px 20px;
    nav {
      display: none;
    }
    select {
      display: none;
    }
    .logo {
      width: 25%;
      float: left;
    }
    i {
      float: right;
      font-size: 30px;
      cursor: pointer;
    }
  }
  
  @media screen and (min-width: 321px) {
    header {
      padding: 20px 40px;
      nav {
        width: 50%;
        display: block;
        li {
          display: inline-block;
          cursor: pointer;
          width: 30%;
          a {
            text-decoration: none;
            color: #000;
            text-align: center;
            padding: 2px 10px;
            &:hover {
              border-bottom: 2px solid #2828ff;
            }
          }
        }
      }
      select {
        display: block;
        float: right;
        border: none;
        text-align: right;
        cursor: pointer;
        appearance: none;
        -webkit-appearance: none;
        -moz-appearance: none;
      }
      i {
        display: none;
      }
    }
  }
</style>