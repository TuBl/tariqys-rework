<template>
  <section class="container" :class="!light ? 'container--alt' : ''">
    <div class="container__sun">
      <img src="~assets/sun.svg" alt="sun icon for light theme" />
    </div>
    <div
      class="container__themeswitcher"
      :class="!light ? 'container__themeswitcher--alt' : ''"
      @click="switchtheme"
    >
      <div class="container__circle"></div>
    </div>
    <div class="container__moon">
      <img src="~assets/moon.svg" alt="moon icon for dark theme" />
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      colors: ['system', 'light', 'dark'],
      light: true,
    }
  },
  methods: {
    switchtheme() {
      this.light = !this.light
      this.light
        ? (this.$colorMode.preference = 'light')
        : (this.$colorMode.preference = 'dark')
    },
  },
}
</script>

<style lang="scss" scoped>
img {
  width: 100%;
}
.container {
  background: #151515;
  height: auto;
  width: 18rem;
  padding: 0.8rem;
  border-radius: 50%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-left: auto;
  mix-blend-mode: normal;
  border-radius: 83px;
  position: relative;
  &__themeswitcher {
    background: #c4c4c4;
    margin-left: -3rem;
    height: 3.2rem;
    width: 3.2rem;
    border-radius: 50%;
    transition: margin-left 200ms ease-in;
    &--alt {
      background: #151515;
      margin-left: 3rem;
      transition: margin-left 200ms ease-in;
    }
  }
  &--alt {
    background: #fefefe;
  }
}
@media only screen and(max-width: 1440px) {
  img {
    width: 65%;
  }
  .container {
    width: 16rem;
    padding: 1rem;
  }
}
@media only screen and(max-width: 768px) {
  img {
    width: 50%;
  }
  .container {
    width: 14rem;
    padding: 0.6rem;
    &__themeswitcher {
      height: 2rem;
      width: 2rem;
      margin-left: -2.5rem;
      &--alt {
        margin-left: 2.5rem;
      }
    }
    &--alt {
      width: 14rem;
      padding: 0.6rem;
    }
  }
}
@media only screen and(max-width: 425px) {
  img {
    width: 50%;
  }
  .container {
    width: 11rem;
    padding: 0.6rem;
    &__themeswitcher {
      height: 1rem;
      width: 1rem;
      margin-left: -0.4rem;
      &--alt {
        margin-left: 0.4rem;
      }
    }
    &--alt {
      width: 11rem;
      padding: 0.6rem;
    }
  }
}
</style>
