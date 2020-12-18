<template>
  <section class="card">
    <div class="card__overlay">
      <p>Tariq Elmughrabi</p>
      <br />
      <p class="p2">Software Developer</p>
    </div>
    <div class="card__circle"></div>
  </section>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.card {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 650px;
  width: 650px;
  &__circle {
    width: 450px;
    height: 439px;
    border-radius: 50%;
    position: absolute;
    top: 15%;
    left: 15.5%;
    z-index: 0;
    background: radial-gradient(
        100% 104.12% at 0% 49.91%,
        #f46c2d 0%,
        rgba(245, 110, 40, 0) 100%
      ),
      radial-gradient(
        96% 99.96% at 100% 49.91%,
        #e64467 0%,
        rgba(230, 68, 103, 0) 100%
      ),
      radial-gradient(
        97.12% 97.12% at 50% 2.88%,
        #ffffff 0%,
        rgba(255, 255, 255, 0) 100%
      );
  }
  &__overlay {
    // background: url('~assets/Rectangle.png') 50% 50% no-repeat;
    width: 411px;
    height: 658px;
    border-radius: 40px;
    mix-blend-mode: overlay;
    z-index: 10;
    background-image: url('~assets/noiseb.png'),
      radial-gradient(
        97.27% 97.27% at 0% 2.73%,
        rgba(255, 255, 255, 0.4) 0%,
        rgba(255, 255, 255, 0) 100%
      );
    backdrop-filter: blur(42px);
    border: 2px solid transparent;
    background-clip: padding-box;
    display: flex;
    color: #ffffff;
    // border-right: 2px solid var(--primary-color);
    // border-top-right-radius: 50%;
    // background-color: rgba(255, 255, 255, 0.1);
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: center;
    text-align: center;
    font-size: 2rem;
    font-family: Moul;
    font-style: normal;
    font-weight: normal;
    p {
      letter-spacing: 0.13em;
    }
    .p2 {
      margin-bottom: 15rem;
    }
  }
}
.card:hover {
  transform: skew(5deg);
  transition: transform 200ms ease-in;
}

@media only screen and(max-width: 1480px) {
  .card {
    &__overlay {
      width: 381px;
      height: 628px;
    }
    &__circle {
      width: 420px;
      height: 409px;
      top: 15%;
      left: 17.5%;
    }
  }
}
@media only screen and(max-width: 1024px) {
  .card {
    &__overlay {
      width: 341px;
      height: 568px;
      font-size: 1.8rem;
      .p2 {
        margin-bottom: 12rem;
      }
    }
    &__circle {
      width: 380x;
      height: 369px;
      top: 15%;
      left: 17.5%;
    }
  }
}
@media only screen and(max-width: 980px) {
  .card {
    &__overlay {
      width: 325px;
      height: 450px;
      font-size: 1.8rem;
      .p2 {
        margin-bottom: 12rem;
      }
    }
    &__circle {
      width: 350px;
      height: 350px;
      top: 15%;
      left: 23.2%;
    }
  }
}
@media only screen and(max-width: 480px) {
  .card {
    &__overlay {
      width: 225px;
      height: 350px;
      font-size: 1.3rem;
      .p2 {
        margin-bottom: 4em;
      }
    }
    &__circle {
      width: 250px;
      height: 250px;
      top: 15%;
      left: 30%;
    }
  }
}
</style>
