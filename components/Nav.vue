<template>
  <header>
    <nav>
      <ul>
        <nuxt-link to="/"><li>Home</li></nuxt-link>
        <nuxt-link to="/projects"><li>Projects</li></nuxt-link>
        <nuxt-link to="/blog"><li>Blog</li></nuxt-link>
      </ul>
      <theme-switcher></theme-switcher>
    </nav>
  </header>
</template>

<script>
import ThemeSwitcher from './ThemeSwitcher.vue'
export default {
  components: { ThemeSwitcher },
}
</script>

<style lang="scss" scoped>
header {
  width: 100%;
  font-family: 'Inter';
  font-style: normal;
  font-weight: normal;
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
@media only screen and(max-width: 480px) {
  header {
    display: flex;
    justify-content: center;
  }
  nav {
    flex-direction: column;
    margin-top: 2rem;
    ul {
      margin-bottom: 2rem;
    }
  }
}
</style>
