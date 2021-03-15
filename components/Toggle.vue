<template>
  <section class="container" :class="!light ? 'container--alt' : ''">
<svg width="40" height="20" viewBox="0 0 40 20" fill="none" xmlns="http://www.w3.org/2000/svg" @click="switchtheme(light)">
<g id="Group 1">
<rect id="Rectangle 1" width="40" height="20" rx="10" fill="#323232"/>
<circle id="circle" cx="30" cy="10" r="6" fill="#FEFEFE" :class = "!light ? 'off' : 'on'"/>
</g>
</svg>
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
    switchtheme(theme) {
      // eslint-disable-next-line no-unused-expressions
      theme === true
        ? ((this.$colorMode.preference = 'dark'), (this.light = false))
        : ((this.$colorMode.preference = 'light'), (this.light = true))
    },
  },
}
</script>

<style lang="scss" scoped>
svg {
  width: 100%;
}
.container {
  margin-left: auto;
}
.on {
  transition: transform 100ms ease-in-out;
}
.off {
  transform: translateX(-20px);
  transition: transform 100ms ease-in-out;
}
</style>
