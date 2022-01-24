<template>
  <div class="">
    <h1 class="text-center text-red-300 font-bold text-2xl">
      This is the results page
    </h1>
    <nav class="flex justify-around">
      <nuxt-link
        class="
          transition
          ease-in-out
          duration-200
          text-lg
          font-semibold
          hover:text-yellow-400 hover:underline
        "
        v-for="link in links"
        :to="{ name: link.link }"
        :key="link.id"
      >
        {{ link.name }}</nuxt-link
      >
    </nav>
    <nuxt-child />
    <p>{{ results }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          name: 'fixtures',
          link: 'results-fixtures',
        },
        {
          name: 'Durham',
          link: 'results-durham-league',
        },
        {
          name: 'Tribal league',
          link: 'results-tribal-league',
        },
        {
          name: 'friendlies',
          link: 'results-friendlies',
        },
      ],
    }
  },

  async asyncData({ $content }) {
    const results = await $content('results').fetch()

    return { results }
  },
}
</script>