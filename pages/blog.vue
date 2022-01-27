<script>
export default {
  async asyncData({ $content }) {
    const blog = await $content('blog').fetch()

    return { blog }
  },
}
</script>

<template>
  <div>
    <h2>Our blog page</h2>
    <nuxt-child />
  </div>
</template>