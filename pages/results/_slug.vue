<template>
  <div>
    <p class="text-xl font-bold my-2 capitalize">
      {{ review.title }}
    </p>
    <nuxt-content :document="review" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const review = await $content('results', params.slug).fetch()

    return { review }
  },
}
</script>