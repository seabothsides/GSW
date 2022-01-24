<script>
export default {
  async asyncData({ $content }) {
    const community = await $content('community').fetch()

    return { community }
  },
}
</script>

<template>
  <div>
    <h2>Our community section</h2>
  </div>
</template>