<template>
  <div class="grid grid-flow-row grid-rows gap-3">
    <div
      v-for="(article, index) in articles"
      :key="index"
      class="
        grid
        auto-rows-min
        md:auto-rows-min
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
          text-lg
          capitalize
          hover:underline hover:text-yellow-400
        "
      >
        {{ article.title }}
      </nuxt-link>
      <p class="p-2 sm:row-start-2 font-light italic">
        {{ article.description }}
      </p>
      <img
        v-if="article.img"
        class="
          rounded-lg
          w-auto
          md:w-4/5
          lg:w-5/6
          md:justify-self-end
          h-min
          object-cover
          order-first
          sm:order-none sm:w-auto sm:col-start-2 sm:row-span-3
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
