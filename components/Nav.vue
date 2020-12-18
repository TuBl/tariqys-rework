<template>
  <header>
    <nav>
      <ul>
        <nuxt-link to="/"><li>Home</li></nuxt-link>
        <nuxt-link to="/projects"><li>Projects</li></nuxt-link>
        <nuxt-link to="/project"><li>Contact</li></nuxt-link>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
header {
  width: 100%;
}
nav {
  display: flex;
  height: 150px;
  align-items: center;
}
ul {
  display: flex;
  color: azure;
  font-size: unquote('clamp(1rem, 3vw, 2rem)');
}
a {
  padding-right: 2rem;
}
a:hover {
  color: var(--primary-color);
  transition: color 100ms ease-in;
}
a:active {
  color: var(--primary-color);
}
.nuxt-link-exact-active {
  color: var(--primary-color);
}
@media only screen and(max-width: 980px) {
  header {
    display: flex;
    justify-content: center;
  }
}
</style>
