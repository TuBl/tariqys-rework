<template>
  <div class="main__layout">
    <Nav></Nav>
    <Nuxt />
  </div>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Moul&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Montserrat+Alternates&display=swap');

html {
  font-family: Montserrat Alternates, 'Source Sans Pro', -apple-system,
    BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  background: #151515;
}

:root {
  --primary-color: #e64467;
  --alternate-color: #f46c2d;
}
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
ul {
  list-style: none;
}
a {
  text-decoration: none;
  color: #fefefe;
}

.main__layout {
  width: 80vw;
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
@media only screen and(max-width: 480px) {
  .main__layout {
    width: 100vw;
  }
}
</style>
