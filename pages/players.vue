<script>
export default {
  async asyncData({ $content }) {
    const players = await $content('players/data').fetch()

    return { players }
  },
}
</script>

<template>
  <div>
    <h2>Some title</h2>
    <div v-for="(player, index) in players.data" :key="index">
      <p>
        {{ player.name }}
      </p>
      <p>
        {{ player.number }}
      </p>
    </div>
    <p>{{ players }}</p>
  </div>
</template>