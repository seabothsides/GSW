<template>
  <div>
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
      <nuxt-link :to="{ name: 'community' }"> back to articles </nuxt-link>
    </button>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('community', params.slug).fetch()

    return { article }
  },
}
</script>