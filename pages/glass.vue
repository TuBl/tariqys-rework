<template>
  <section class="container">
    <Card class="container__card"></Card>
    <div class="container__text">
      <h1>
        I Build Amazing <br />
        Web Experiences..
      </h1>
      <h4>Lets Build Something for you</h4>
      <nuxt-link to="/projects" class="container__button">Portofolio</nuxt-link>
    </div>
  </section>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style lang="scss" scoped>
.container {
  // background: red;
  width: 80vw;
  height: 80vh;
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: #e5e5e5;
  text-align: justify;
  &__text {
    width: 50%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    h1 {
      font-family: Moul;
      font-style: normal;
      font-weight: normal;
      font-size: unquote('clamp(1.5rem, 3vw, 4rem)');
      line-height: 4.75rem;
      letter-spacing: 0.13em;
      margin-top: -5.5rem;
      animation: slide-left 1000ms;
    }
    h4 {
      font-size: unquote('clamp(.9rem, 2vw, 2.25rem)');
      line-height: 2.75rem;
      letter-spacing: 0.13em;
      animation: slide-right 1000ms;
    }
  }
  &__button {
    background: radial-gradient(
        84.24% 527.68% at 80% 50.25%,
        #e64467 0%,
        rgba(230, 68, 103, 0) 100%,
        rgba(230, 68, 103, 0.5) 100%
      ),
      radial-gradient(
        50.1% 321.45% at 0% 50.25%,
        #f46c2d 0%,
        rgba(244, 108, 45, 0.5) 100%
      );
    mix-blend-mode: normal;
    border-radius: 17px;
    width: 100%;
    padding: unquote('clamp(1rem, 2vw, 2rem)');
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    font-family: Moul;
    font-style: normal;
    font-weight: normal;
    font-size: unquote('clamp(1rem, 3.5vw, 3rem)');
    animation: slide-up 1000ms;
  }
}
// @media only screen and(max-width: 1480px) {
//   .container {
//     background-position: -50% 50%;
//     background-size: 70% 70%;
//   }
// }
@media only screen and(max-width: 1480px) {
  .container {
    flex-direction: column;
    align-items: flex-start;
    &__card {
      align-self: flex-end;
      margin-right: -7.5rem;
    }
    &__text {
      justify-content: center;
      h1 {
        line-height: 2.75rem;
      }
      h1,
      h4 {
        margin-bottom: 2rem;
        letter-spacing: 0em;
      }
    }
    &__button {
      padding: 0.8rem;
    }
  }
}
@media only screen and(max-width: 1024px) {
  .container {
    &__card {
      margin-right: -8.5rem;
    }
  }
}
@media only screen and(max-width: 980px) {
  .container {
    width: 100vw;
    align-items: center;
    margin-bottom: -5rem;
    &__card {
      margin-right: 0;
      align-self: center;
      margin-bottom: 3.5rem;
    }
    &__text {
      text-align: center;
      h1,
      h4 {
        margin-bottom: 1rem;
        letter-spacing: 0em;
      }
    }
  }
}

</style>
