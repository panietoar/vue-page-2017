<template>
  <section id="contact">
    <h2 class="title"> {{ contact.title }}</h2>
    <div class="message">{{ contact.message }}</div>

    <div class="contact-form">
      <h3>{{ contact.formName }}</h3>
      <form action="#">
        <input type="text" name="" id="" :placeholder="contact.name">
        <input type="text" name="" id="" :placeholder="contact.lastName">
        <select type="text" name="" id="" :placeholder="contact.country">
          <option value="">Colombia</option>
        </select>
        <input type="text" name="" id="" :placeholder="contact.email">

        <div class="interests">
          <header >{{ contact.interestHeader }}</header>
          <div class="checboxes">
            <div v-for="(checkbox, index) in contact.checkboxes" :key="index">
              <input type="checkbox" :id="'option' + index">
              <label :for="'option' + index">{{ checkbox.label }}</label>
            </div>
          </div>
        </div>

        <button type="button">{{ contact.cta }}</button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  props:['contact']

}
</script>

<style scoped lang="scss">
  section {
    margin: 1.5em 18px;

    h2 {
      font-family: 'Montserrat', sans-serif;
      text-transform: uppercase;
      font-size: 12px;
    }

    .contact-form {
      margin-top: 3em;

      h3 {
        text-transform: uppercase;
        font-size: 12px;
      }

    }
  }
</style>
