<template>
  <div class="grid grid-auto-row gap-3">
    <div
      v-for="(articles, index) in articles"
      :key="index"
      class="p-2 border rounded-lg border-4 border-gray-400"
    >
      <nuxt-link
        :to="{ name: 'blog-slug', params: { slug: articles.slug } }"
        class="font-semibold capitalize hover:underline hover:text-yellow-400"
      >
        {{ articles.title }}
      </nuxt-link>
      <p class="font-light">
        {{ articles.description }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const articles = await $content('blog').sortBy('createdAt', 'desc').fetch()

    return { articles }
  },
}
</script>