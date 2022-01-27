<template>
  <div>
    <p class="text-xl font-bold my-2 capitalize">
      {{ article.title }}
    </p>
    <nuxt-content :document="article" />
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