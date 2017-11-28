<template>
  <section class="main-heading" id="about">
    <div>
      {{ content }}
    </div>
  </section>
</template>

<script>
  export default {
    props: [
      'content'
    ]
  }
</script>

<style scoped lang="scss">
  section {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 55%;
    div {
      font-size: 30px;
      width: 95%;
      line-height: 1;
    }
  }
  
  @media screen and (min-width: 321px) {
    section {
      height: 40%;
      div {
        font-size: 60px;
        width: 65%;
      }
    }
  }
</style>