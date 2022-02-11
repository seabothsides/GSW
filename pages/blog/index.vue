<template>
  <div class="grid grid-flow-row gap-3">
    <div
      v-for="(article, index) in articles"
      :key="index"
      class="
        grid
        auto-rows-min
        grid-flow-row-dense
        border
        rounded-lg
        border-4 border-gray-400
        overflow-auto
      "
    >
      <nuxt-link
        :to="{ name: 'blog-slug', params: { slug: article.slug } }"
        class="
          p-2
          font-semibold
          capitalize
          hover:underline hover:text-yellow-400
        "
      >
        {{ article.title }}
      </nuxt-link>
      <p class="p-2 row-start-2 font-light">
        {{ article.description }}
      </p>
      <img
        class="
          object-scale-down
          rounded-lg
          w-full
          h-full
          col-start-2
          row-span-2
        "
        :src="article.img"
        alt=""
      />
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