<template>
  <div class="mb-2">
    <p class="text-xl font-bold my-2 capitalize">
      {{ article.title }}
    </p>
    <nuxt-content :document="article" />
    <button
      class="
        hover:bg-yellow-400 hover:text-white
        p-1
        mt-2
        rounded-lg
        capitalize
        font-bold
      "
    >
      <nuxt-link :to="{ name: 'blog' }"> back to articles </nuxt-link>
    </button>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('blog', params.slug).fetch()

    return { article }
  },
}
</script>

<style>
.nuxt-content {
  display: grid;
  grid-auto-flow: row;
  gap: 1.15em;
}
</style>