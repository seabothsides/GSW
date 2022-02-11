<template>
  <div class="">
    <h1
      class="
        hidden
        capitalize
        pb-2
        text-4xl
        font-bold
        italic
        bg-clip-text bg-gradient-to-br
        from-yellow-400
        to-pink-400
        text-transparent
      "
    >
      This is the results page
    </h1>
    <nav
      class="flex justify-around my-4 border-r-4 border-l-4 border-yellow-500"
    >
      <nuxt-link
        class="
          transition
          ease-in-out
          duration-200
          text-lg
          font-semibold
          hover:text-yellow-400 hover:underline
          capitalize
        "
        v-for="link in links"
        :to="{ name: link.link }"
        :key="link.id"
      >
        {{ link.name }}</nuxt-link
      >
    </nav>
    <nuxt-child />
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          name: 'fixtures',
          link: 'results',
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
}
</script>