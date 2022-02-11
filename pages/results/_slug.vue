<template>
  <div>
    <p class="text-xl font-bold my-2 capitalize">
      {{ review.title }}
    </p>
    <nuxt-content :document="review" />
    <button
      class="
        hover:bg-yellow-400 hover:text-white
        p-1
        mt-2
        rounded-lg
        capitalize
        font-bold
        border border-3 border-yellow-500
      "
      @click="back"
    >
      back to results
    </button>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const review = await $content('results', params.slug).fetch()

    return { review }
  },
  methods: {
    back() {
      this.$router.go(-1)
    },
  },
}
</script>