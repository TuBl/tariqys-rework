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
      <Social class="container__icons"></Social>
    </div>
  </section>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 80vh;
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-align: justify;
  color: #e5e5e5;
  &__card {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    width: 50%;
    height: 100%;
  }
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
      font-size: unquote('clamp(1.2rem, 2.5vw, 4rem)');
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
@media only screen and(max-width: 1268px) {
  .container {
    flex-direction: row-reverse;
    justify-content: space-between;
    &__card {
      padding-bottom: 9rem;
      justify-content: flex-end;
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
      margin-bottom: 1rem;
    }
  }
}
@media only screen and(max-width: 768px) {
  .container {
    flex-direction: column;
    &__card {
      padding-bottom: 0rem;
      align-self: flex-end;
    }
    &__text {
      align-self: flex-start;
    }
  }
}
@media only screen and(max-width: 725px) {
  .container {
    justify-content: center;
    align-items: center;
    &__card {
      align-self: center;
    }
    &__text {
      align-self: center;
      text-align: center;
    }
  }
}
</style>
