<template>
  <div class="blog-container">
    <blog-post
      v-for="article in articles"
      :key="article.id"
      :title="article.title"
      :abstract="article.description"
      :duration="article.duration"
      :date="article.updatedAt"
      :category="article.category"
      :author="article.author"
      :info1="article.info1"
      :info2="article.info2"
      :info3="article.info3"
      :slug="article.slug"
    ></blog-post>
  </div>
</template>

<script>
import BlogPost from '~/components/BlogPost.vue'
export default {
  components: { BlogPost },
  async asyncData({ $content }) {
    // Fetch returns promise
    const articles = await $content('articles').fetch()
    return {
      articles,
    }
  },
}
</script>

<style lang="scss" scoped>
.blog-container {
  display: grid;
  justify-items: start;
  text-align: justify;
  height: 100vh;
  width: 100%;
  margin-top: 5rem;
}
.nuxt-content a {
  color: red;
}

li {
  list-style-type: disc;
  margin-left: 1.5em;
}

blockquote {
  background-image: initial;
  background-color: rgb(27, 30, 31);
  border-left-color: rgb(62, 68, 70);
  background: #f9f9f9;
  border-left: 10px solid #ccc;
  margin: 1.5em 10px;
  padding: 1em 10px 0.5em 10px;
  quotes: '\201C''\201D''\2018''\2019';
}
</style>
