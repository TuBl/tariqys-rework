<template>
  <div
    class="blog-post-container"
    :class="
      this.$colorMode.preference == 'dark' ? 'blog-post-container--alt' : ''
    "
  >
    <nuxt-img
      :src="`/blog/${article.image}`"
      sizes="sm:250px md:50vw lg:1740px"
    />
    <h1>{{ article.title }}</h1>
    <table-of-content
      :toc="article.toc"
      class="blog-post-container__toc"
      :class="
        this.$colorMode.preference == 'dark'
          ? 'blog-post-container__toc--alt'
          : ''
      "
    ></table-of-content>
    <nuxt-content
      :document="article"
      :class="
        this.$colorMode.preference == 'dark'
          ? 'nuxt-content-container--alt'
          : ''
      "
    />
  </div>
</template>

<script>
import TableOfContent from '~/components/TableOfContent.vue'
export default {
  components: { TableOfContent },
  async asyncData({ $content, route }) {
    const article = await $content(`articles/${route.params.slug}`).fetch()
    return {
      article,
    }
  },
}
</script>

<style lang="scss">
.blog-post-container {
  display: grid;
  justify-items: center;
  text-align: justify;
  height: auto;
  min-height: 100vh;
  width: 100%;
  margin-top: 5rem;
  grid-template-rows: auto auto auto auto;
  grid-template-columns: 1fr;
  grid-template-areas:
    'hero'
    'aside'
    'title'
    'main';
  img {
    grid-area: hero;
    max-height: 500px;
    width: 100%;
    border-radius: 1rem;
    margin-bottom: 3rem;
  }
  h1 {
    grid-area: title;
    color: var(--blog-primary);
    width: 100%;
    font-size: calc(1rem + (3.825 - 1) * (100vw - 30rem) / (123.75 - 30));
    text-align: justify;
    margin-bottom: 3rem;
  }
  .icon.icon-link {
    background-image: url('~assets/icon-hashtag.svg');
    display: inline-block;
    width: 0.8em;
    height: 0.8em;
    background-size: 0.8em 0.8em;
  }
  &__toc {
    grid-area: aside;
    height: auto;
    max-height: 500px;
    border-radius: 10px;
    width: 100%;
    justify-self: center;
    margin-bottom: 3rem;
    background: rgba(168, 165, 165, 0.3);
    h2 {
      color: var(--blog-primary);
      font-size: unquote('clamp(.9rem, 2vw, 1.7rem)');
      padding: 0.4em;
    }
    li {
      padding: 0.8em;
      padding-left: 1.2em;
      font-size: unquote('clamp(.8rem, 2vw, 1rem)');
    }
    li:hover {
      background: rgba(179, 174, 174, 0.4);
      transition: background 100ms ease-in-out;
    }
    a:hover {
      color: var(--blog-primary);
      transition: color 100ms ease-in-out;
    }
    &--alt {
      background: rgba(93, 91, 91, 0.4);
      .icon.icon-link {
        background-image: url('~assets/icon-hashtag-alt.svg');
      }
      h2 {
        color: var(--blog-dark--primary);
        padding: 0.4em;
      }
      li {
        padding: 0.8em;
        padding-left: 1.2em;
      }
      li:hover {
        background: rgba(107, 105, 105, 0.4);
        transition: background 100ms ease-in-out;
      }
      a:hover {
        color: var(--blog-dark--primary);
        transition: color 100ms ease-in-out;
      }
    }
  }
  .nuxt-content-container {
    grid-area: main;
    width: 100%;
    p,
    li {
      margin-bottom: 1rem;
      margin-left: 10px;
    }
    blockquote {
      background-color: rgb(27, 30, 31);
      border-left-color: var(--blog--primary);
      background: #f9f9f9;
      border-left: 10px solid #ccc;
      margin: 1.5em 10px;
      padding: 1em 10px 0.1em 10px;
      quotes: '\201C''\201D''\2018''\2019';
    }
    &--alt {
      color: var(--blog-alternate);

      blockquote {
        border-left-color: rgba(244, 108, 45, 0.9);
        p,
        li,
        h2,
        h3,
        h4 {
          color: var(--blog-dark--alternate);
        }
      }
      .icon.icon-link {
        background-image: url('~assets/icon-hashtag-alt.svg');
        display: inline-block;
        width: 0.8em;
        height: 0.8em;
        background-size: 0.8em 0.8em;
        transition: background-image 100ms ease-in;
      }
    }
  }
  &--alt {
    h1 {
      color: var(--blog-dark--primary);
    }
  }
}
</style>
