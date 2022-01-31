<template>
  <div>
    <h1 class="text-2xl font-bold capitalize">friendly game results</h1>
    <div v-for="result in results" :key="result.id" class="py-3">
      <nuxt-link
        :to="{ name: 'results-slug', params: { slug: result.slug } }"
        class="
          font-semibold
          hover:underline hover:text-yellow-400
          capitalize
          text-lg
        "
      >
        {{ result.title }}
      </nuxt-link>
      <p class="font-light italic">
        {{ formatDate(result.date) }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const results = await $content('results')
      .where({ league: 'friendly' })
      .fetch()

    return { results }
  },
  methods: {
    formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    },
  },
}
</script>