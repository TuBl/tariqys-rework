<template>
  <div class="blog-post-container">
    <img :src="`/blog/${article.image}`" />
    <nuxt-content
      :document="article"
      :class="this.$colorMode.preference == 'dark' ? 'nuxt-content--alt' : ''"
    />
  </div>
</template>

<script>
export default {
  async asyncData({ $content, route }) {
    const article = await $content(`articles/${route.params.slug}`).fetch()
    return {
      article,
    }
  },
  beforeUpd() {
    console.log(this.$colorMode.preference)
  },
}
</script>

<style lang="scss">
.blog-post-container {
  display: grid;
  justify-items: center;
  text-align: justify;
  height: 100vh;
  width: 100%;
  margin-top: 5rem;
  img {
    height: auto;
    max-height: 500px;
    width: 100%;
    border-radius: 1rem;
    margin-bottom: 3rem;
  }
}
.nuxt-content {
  h1 {
    color: var(--blog-primary);
    font-size: calc(1rem + (3.825 - 1) * (100vw - 30rem) / (123.75 - 30));
    text-align: center;
    margin-bottom: 3rem;
  }
  .article-container {
    padding-left: 5rem;
    width: 80%;
    p,
    li {
      margin-bottom: 1rem;
    }
    blockquote {
      background-color: rgb(27, 30, 31);
      border-left-color: rgb(62, 68, 70);
      background: #f9f9f9;
      border-left: 10px solid #ccc;
      margin: 1.5em 10px;
      padding: 1em 10px 0.1em 10px;
      quotes: '\201C''\201D''\2018''\2019';
    }
  }

  &--alt {
    h1 {
      color: var(--blog-dark--primary);
    }
    p,
    li {
      color: var(--blog-alternate);
    }
    blockquote p {
      color: var(--blog-dark--alternate);
    }
  }
}
</style>
