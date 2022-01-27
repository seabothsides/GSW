<template>
  <nav
    class="
      bg-gray-200
      px-3
      md:px-8
      lg:px-56
      md:py-1.5
      flex
      justify-between
      lg:grid
      grid-cols-2
      items-center
    "
  >
    <nuxt-link
      class="font-bold text-2xl md:text-3xl hover:text-yellow-400"
      to="/"
      >Brand Logo</nuxt-link
    >
    <div class="flex space-x-1 md:space-x-3 lg:space-x-7 capitalize">
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
    </div>
    <div
      class="
        grid grid-auto-row
        md:hidden
        z-20
        md:space-x-3
        lg:space-x-7
        capitalize
      "
    >
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
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          name: 'about',
          link: 'about',
        },
        {
          name: 'players',
          link: 'players',
        },
        {
          name: 'results',
          link: 'results',
        },
        {
          name: 'blog',
          link: 'blog',
        },
        {
          name: 'community',
          link: 'community',
        },
        {
          name: 'shop',
          link: 'shop',
        },
      ],
    }
  },
}
</script>