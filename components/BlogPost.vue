<template>
  <article>
    <nuxt-link v-if="preview" :to="article.slug"
      ><h2>{{ article.title }}</h2></nuxt-link
    >
    <h2 v-else class="mb-6">{{ article.title }}</h2>
    <div
      class="wrapper"
      :class="preview ? 'flex flex-wrap md:flex-nowrap flex-row ' : ''"
    >
      <div>
        <img
          :src="article.img"
          :alt="article.title"
          :class="preview ? 'max-w-md rounded-xl mr-3 mt-3' : 'rounded-xl mb-8'"
        />
      </div>
      <div class="m-3">
        <ul class="mb-2">
          <li
            v-for="tag in article.tags"
            :key="tag"
            class="rounded-md border border-green-800 px-2 py-1 text-xs w-min text-green-800 inline-block mr-2"
          >
            {{ tag }}
          </li>
        </ul>
        <div class="text-gray-500 text-xs mt-4 mb-2">
          {{ formatDate(article.updatedAt) }}
        </div>
        <p v-if="preview">{{ article.description }}</p>
        <nuxt-content v-else :document="article" />
        <nuxt-link v-if="preview" :to="article.slug"
          ><button>Weiterlesen</button></nuxt-link
        >
      </div>
    </div>
  </article>
</template>

<script>
export default {
  props: {
    article: {
      type: Object,
      required: true,
      default() {
        return {
          title: 'Post Title',
          description: 'Post Description',
          tags: ['tagname'],
          img: '/link/to/your/image.file',
        }
      },
    },
    preview: {
      type: Boolean,
      default: true,
    },
  },
  methods: {
    formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('de', options)
    },
  },
}
</script>
