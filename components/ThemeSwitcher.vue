<template>
  <section class="container" :class="!light ? 'container--alt' : ''">
    <div class="container__sun">
      <!-- <img src="~assets/sun.svg" alt="sun icon for light theme" />
       -->
      <svg
        width="66"
        height="68"
        viewBox="0 0 66 68"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          id="Vector"
          d="M51.3333 34C51.3333 44.4342 43.1273 52.8889 33 52.8889C22.8727 52.8889 14.6667 44.4342 14.6667 34C14.6667 23.5658 22.8727 15.1111 33 15.1111C43.1273 15.1111 51.3333 23.5658 51.3333 34ZM33 7.55556C34.2467 7.55556 35.464 7.68022 36.6667 7.85778V0H29.3333V7.85778C30.536 7.68022 31.7533 7.55556 33 7.55556ZM17.6587 12.8482L12.2613 7.28356L7.073 12.6291L12.474 18.1938C13.948 16.1651 15.6933 14.3669 17.6587 12.8482V12.8482ZM53.526 18.19L58.927 12.6253L53.7423 7.28356L48.3413 12.8482C50.3103 14.3669 52.052 16.1651 53.526 18.19ZM33 60.4444C31.7533 60.4444 30.536 60.3198 29.3333 60.1422V68H36.6667V60.1422C35.464 60.3198 34.2467 60.4444 33 60.4444ZM48.345 55.148L53.746 60.7127L58.9343 55.3671L53.5333 49.8062C52.0557 51.8311 50.3103 53.6293 48.345 55.148ZM7.33333 34C7.33333 32.7156 7.45433 31.4613 7.62667 30.2222H0V37.7778H7.62667C7.45433 36.5387 7.33333 35.2844 7.33333 34ZM58.3733 30.2222C58.5457 31.4613 58.6667 32.7156 58.6667 34C58.6667 35.2844 58.5457 36.5387 58.3733 37.7778H66V30.2222H58.3733V30.2222ZM12.4703 49.8062L7.06933 55.3709L12.254 60.7127L17.655 55.148C15.6897 53.6293 13.9443 51.8349 12.4703 49.8062Z"
          class="container__sun-svg"
          :class="!light ? 'container__sun-svg--alt' : ''"
        />
      </svg>
    </div>
    <div
      class="container__themeswitcher"
      :class="!light ? 'container__themeswitcher--alt' : ''"
      @click="switchtheme"
    >
      <div class="container__circle"></div>
    </div>
    <div class="container__moon">
      <!-- <img src="~assets/moon.svg" alt="moon icon for dark theme" /> -->
      <svg
        width="66"
        height="68"
        viewBox="0 0 66 68"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <g id="iconmonstr-weather-114 1" clip-path="url(#clip0)">
          <path
            id="Vector"
            d="M33 31.1638C36.9518 32.4048 40.0455 35.5952 41.2472 39.6667C42.4572 35.5952 45.551 32.4077 49.5 31.1667C45.551 29.9228 42.4572 26.7382 41.2472 22.6667C40.0455 26.7353 36.9518 29.9228 33 31.1638ZM55.0027 31.1667C57.6372 31.9968 59.697 34.119 60.5027 36.8362C61.303 34.119 63.3682 31.994 66 31.1667C63.3682 30.3393 61.3058 28.2143 60.5 25.5C59.6942 28.2143 57.6345 30.3393 55.0027 31.1667ZM52.2527 5.66667C51.051 9.73817 47.9545 12.9257 44.0083 14.1695C47.9628 15.4162 51.051 18.6008 52.261 22.6752C53.4627 18.6008 56.5593 15.4133 60.5 14.1695C56.5593 12.9313 53.4627 9.73817 52.2527 5.66667V5.66667ZM33 68C14.8032 68 0 52.7482 0 34C0 15.2518 14.8032 0 33 0C38.2085 0 42.9825 1.40817 47.7675 3.3405C39.6605 4.7685 22 12.5942 22 34C22 55.1197 38.2718 62.9227 47.7675 64.6595C43.6425 67.0565 38.2085 68 33 68V68Z"
            fill="#E64467"
            class="container__moon-svg"
            :class="!light ? 'container__moon-svg--alt' : ''"
          />
        </g>
        <defs>
          <clipPath id="clip0">
            <rect width="66" height="68" fill="white" />
          </clipPath>
        </defs>
      </svg>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
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
  background: var(--switcher-alt);
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
  &__sun {
    &-svg {
      fill: var(--moon);
    }
  }
  &__moon {
    &-svg {
      fill: var(--sun);
    }
  }
  &__themeswitcher {
    background: var(--switcher-bg);
    margin-left: -3rem;
    height: 3.2rem;
    width: 3.2rem;
    border-radius: 50%;
    transition: margin-left 200ms ease-in;
    &--alt {
      margin-left: 3rem;
      transition: margin-left 200ms ease-in;
    }
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
