<template>
  <div class="blog-post-container">
    <nuxt-content :document="page" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content, route }) {
    const page = await $content(`articles/${route.params.slug}`).fetch()
    return {
      page,
    }
  },
}
</script>

<style>
.blog-post-container {
  display: grid;
  justify-items: start;
  text-align: justify;
  height: 100vh;
  width: 100%;
  margin-top: 5rem;
}
</style>
