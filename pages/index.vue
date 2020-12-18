<template>
  <section class="container">
    <!-- <CardCopy class="container__card"></CardCopy> -->
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
  width: 100%;
  height: 80vh;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  color: #e5e5e5;
  text-align: justify;
  background: url('~assets/bgcard.svg') no-repeat 0% 50%;
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
@media only screen and(max-width: 1480px) {
  .container {
    background-position: -50% 50%;
    background-size: 70% 70%;
  }
}
@media only screen and(max-width: 1268px) {
  .container {
    flex-direction: column;
    align-items: flex-start;
    background-position: 100% 35%;
    background-size: 40% 40%;
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

@media only screen and(max-width: 480px) {
  .container {
    width: 100vw;
    background-position: 50% 0%;
    background-size: 50% 50%;
    align-items: center;

    &__text {
      justify-content: flex-end;
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
