<template>
  <blog-post :article="article" :preview="false"></blog-post>
</template>

<script>
import BlogPost from '../components/BlogPost.vue'
export default {
  components: { BlogPost },
  async asyncData({ $content, params }) {
    const article = await $content('blog', params.slug).fetch()
    return { article }
  },
}
</script>
