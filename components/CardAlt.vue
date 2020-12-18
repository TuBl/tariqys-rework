<template>
  <section class="card">
    <div class="card__overlay">
      <p>Tariq</p>
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
  &__circle {
    width: 550px;
    height: 539px;
    left: 157px;
    top: 308px;
    border-radius: 50%;
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
    background: url('~assets/Rectangle.png');
    position: absolute;
    width: 411px;
    height: 658px;
    border-radius: 40px;
    mix-blend-mode: overlay;
    background: radial-gradient(
      97.27% 97.27% at 0% 2.73%,
      rgba(255, 255, 255, 0.4) 0%,
      rgba(255, 255, 255, 0) 100%
    );
    backdrop-filter: blur(42px);
    border: 2px solid transparent;
    background-clip: padding-box;
    left: 70px;
    top: -50px;
    display: flex;
    color: #ffffff;
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
      //   opacity: 0.5;
      //   position: absolute;
    }
    .p2 {
      margin-bottom: 10rem;
    }
  }
}
</style>
