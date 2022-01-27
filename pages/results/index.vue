<template>
  <div>
    <h1 class="text-2xl font-bold border-b-2 mb-3">Fixtures</h1>
    <div class="grid grid-cols-2 gap-2">
      <div
        v-for="game in fixtures.fixtures"
        :key="game.id"
        class="
          grid grid-auto-row
          gap-2
          text-center
          border border-2
          py-1
          rounded-md
        "
      >
        <p class="capitalize font-semibold">
          Golden Smog vs {{ game.opponent }}
        </p>
        <p>{{ game.league }}</p>
        <p>{{ formatDate(game.date) }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const fixtures = await $content('fixtures').fetch()

    return { fixtures }
  },
  methods: {
    formatDate(date) {
      const options = {
        year: 'numeric',
        month: 'long',
        day: 'numeric',
        time: 'numeric',
      }
      return new Date(date).toLocaleDateString('en', options)
    },
  },
}
</script>