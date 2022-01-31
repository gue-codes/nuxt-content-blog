<template>
  <section>
    <h1 class="my-10">Blogbeiträge</h1>
    <blog-post
      v-for="article in articles"
      :key="article.title"
      :article="article"
      class="mb-16"
    ></blog-post>
  </section>
</template>

<script>
import BlogPost from '../components/BlogPost.vue'
export default {
  name: 'IndexPage',
  components: { BlogPost },
  async asyncData({ $content }) {
    const articles = await $content('blog').fetch()
    return {
      articles,
    }
  },
}
</script>
