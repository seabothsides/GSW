<template>
  <div class="grid text-center">
    <h1 class="text-6xl capitalize font-bold text-center pt-6 text-red-600">
      {{ index.title }}
    </h1>
    <nuxt-content :document="index" />
    <p class="text-4xl font-bold text-blue-300">Featured components go below</p>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const index = await $content('index').fetch()

    return { index }
  },
}
</script>
