<script>
export default {
  async asyncData({ $content }) {
    const players = await $content('players').fetch()

    return { players }
  },
}
</script>

<template>
  <div>
    <h2>Some title</h2>
    <p>{{ players }}</p>
  </div>
</template>