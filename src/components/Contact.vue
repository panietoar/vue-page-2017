<template>
  <section id="contact">
    <h2 class="title"> {{ contact.title }}</h2>
    <div class="message" v-if="!submitted">{{contact.greeting}} {{name}},<br> {{ contact.message }}</div>
    <div class="message" v-else>{{name}}, {{ contact.thankyou }}</div>

    <div v-if="!submitted" class="contact-form">
      <h3>{{ contact.formName }}</h3>
      <form action="#">
        <fieldset>
          <input type="text" name="" id="name" v-model="name" required>
          <label for="name">{{contact.name}}</label>
        </fieldset>
        <fieldset>
          <input type="text" name="" id="lastname" required>
          <label for="lastname">{{contact.lastName}}</label>
        </fieldset>
       
        <fieldset>
          <input type="text" name="" id="email" required>
          <label for="email">{{contact.email}}</label>
        </fieldset>

        <div class="interests">
          <header>{{ contact.interestHeader }}</header>
          <div class="checkboxes">
            <div v-for="(checkbox, index) in contact.checkboxes" :key="index">
              <input type="checkbox" :id="'option' + index">
              <label :for="'option' + index">{{ checkbox.label }}</label>
            </div>
          </div>
        </div>

        <button type="button" @click="submit">{{ contact.cta }}</button>
      </form>
    </div>
  </section>
</template>

<script>
export default {
  props:['contact'],
  data() {
    return {
      submitted: false,
      name: ''
    }
  },
  methods: {
    submit() {
      // post contact form
      this.submitted = true;
    }
  }

}
</script>

<style scoped lang="scss">

  $formBordersColor: #979797;

  @mixin form-header() {
    text-transform: uppercase;
    font-size: 12px;
  }

  section {
    margin: 1.5em 18px;

    h2 {
      @include form-header();
      font-family: 'Montserrat', sans-serif;
      font-weight: bold;
    }

    .contact-form {
      margin-top: 3em;

      button {
        width: 100%;
        border-radius: 0;
        border-color: #000000;
        color: #000000;
        font-size: 16px;
        height: 3em;
        -webkit-transition: all 0.5s;
        -moz-transition: all 0.5s;
        transition: all 0.5s;

        &:hover {
          background-color: #000;
          color: #FFF;
        }

      }

      h3 {
        @include form-header();
      }

      fieldset {
        position: relative;
        padding: 0;

        label {
          color: #9b9b9b;
          position: absolute;
          top: 16px;
          font-size: 8px;
          font-weight: 100;
          -webkit-transition: all 0.2s  ease;
          -moz-transition: all 0.2s  ease;
          transition: all 0.2s  ease;
        }

        input {
          width: 100%;
          border-color: $formBordersColor;
          border-radius: 0;
          border-top: none;
          border-left: none;
          border-right: none;
          font-family: 'Montserrat', sans-serif;
          font-weight: bold;

          &:focus {
            border-color: $formBordersColor;

            ~ label {
              top: 0;
              color: #000000;
            }
          }

          &:not(:focus):valid ~ label {
            top: 0;
            color: #000000;
          }
        }
      }

      .interests {
        margin-top: 2em;

        header {
          @include form-header();
          border-bottom: 1px solid $formBordersColor;
          margin-bottom: 1.5em;
        }

        .checkboxes {
          display: flex;
          flex-wrap: wrap;
          margin-bottom: 1.5em;

          &>div{
            width: 50%;

            input,
            label {
              display: inline;
              vertical-align: middle;
            }

            label {
              margin-left: 9px;
              font-family: 'Montserrat', sans-serif;
              font-size: 12px;
            }

            input[type=checkbox] {
              transform: scale(1.2);
            }

            input[type=checkbox]:not(:checked) + label {
              color: #9b9b9b;
            }
          }
        }
      }
    }
  }

  @media screen and (min-width: 321px) {
    section {
      width: 60%;
      margin: auto;

      .message {
        font-size: 36px;
        width: 80%;
        margin: 0 0 1em 120px;
      }

      .contact-form {
        width: 60%;
        margin: auto;

        h3 {
          font-family: 'Montserrat', sans-serif;
          font-weight: bold;
        }

      }
    }
  }

</style>
