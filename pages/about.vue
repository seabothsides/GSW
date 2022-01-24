<script>
export default {
  async asyncData({ $content }) {
    const about = await $content('about').fetch()

    return { about }
  },
}
</script>

<template>
  <div>
    <h2>{{ about.title }}</h2>
    <nuxt-content :document="about" class="pt-4" />
  </div>
</template>