<template>
  <div class="wrapper">
    <section class="card">
      <div class="card__overlay">
        <div class="card__text">
          <p>Tariq Elmughrabi</p>
          <br />
          <p class="p2">Software Developer</p>
        </div>
      </div>
      <div class="card__circle"></div>
    </section>
  </div>
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
  font-size: unquote('clamp(1rem, 2vw, 2.2rem)');
  &__circle {
    height: 80%;
    width: 80%;
    border-radius: 50%;
    position: absolute;
    top: 10%;
    left: 10%;
    z-index: 0;
    background: var(--gradient);
  }
  &__overlay {
    height: 100%;
    width: 60%;
    border-radius: 40px;
    mix-blend-mode: overlay;
    z-index: 10;
    background-image: url('~assets/noiseb.png'),
      radial-gradient(
        97.27% 97.27% at 0% 2.73%,
        rgba(255, 255, 255, 0.4) 0%,
        rgba(255, 255, 255, 0) 100%
      );
    background-repeat: no-repeat;
    backdrop-filter: blur(42px);
    border: 2px solid transparent;
    background-clip: padding-box;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: center;
    text-align: center;
    position: relative;
    z-index: 50;
  }
  &__text {
    position: absolute;
    bottom: 0;
    z-index: 100;
    color: #ffffff;
    opacity: 0.75;
    font-family: 'Inter';
    font-style: bold;
    font-weight: bold;
    padding: 0.5rem;
    p {
      letter-spacing: 0.13em;
    }
    .p2 {
      margin-bottom: 35%;
    }
  }
}
@media only screen and(max-width: 1268px) {
  .card {
    height: 350px;
    width: 350px;
  }
}
@media only screen and(max-width: 480px) {
  .card {
    height: 250px;
    &__overlay {
      width: 80%;
    }
    &__circle {
      width: 100%;
      left: 0%;
    }
  }
}
</style>
