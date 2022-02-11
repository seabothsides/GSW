<template>
  <div>
    <nav
      class="
        bg-gray-200
        px-3
        py-1.5
        md:px-8 md:py-1.5
        flex
        justify-between
        lg:grid lg:px-32
        xl:px-56
        grid-cols-2
        items-center
        sm:bg-purple-300
        md:bg-green-300
        lg:bg-red-200
        xl:bg-blue-300
      "
    >
      <p>
        <nuxt-link
          class="font-bold text-2xl md:text-3xl hover:text-yellow-400"
          to="/"
          @click.native="close"
          >Brand Logo</nuxt-link
        >
      </p>
      <div
        class="
          flex
          space-x-1
          sm:space-x-4
          md:space-x-5
          lg:space-x-7
          xl:space-x-12
          capitalize
          hidden
          sm:flex
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
      <button id="nav-button" class="sm:hidden" @click="isOpen">menu</button>
    </nav>
    <div
      id="nav-draw"
      class="
        grid grid-auto-row
        hidden
        sm:hidden
        absolute
        bg-gray-500
        capitalize
        w-screen
        h-screen
        gap-10
        place-content-center
        transition-all
        ease-in-out
        duration-200
        overscroll-none
        overflow-hidden
      "
    >
      <nuxt-link
        class="
          transition
          ease-in-out
          duration-200
          text-4xl
          font-semibold
          hover:text-yellow-400 hover:underline
        "
        v-for="link in links"
        :to="{ name: link.link }"
        :key="link.id"
        @click.native="isOpen"
      >
        {{ link.name }}</nuxt-link
      >
    </div>
  </div>
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
  methods: {
    isOpen() {
      var element = document.getElementById('nav-draw')

      element.classList.toggle('hidden')
    },
    close() {
      var element = document.getElementById('nav-draw')

      element.classList.add('hidden')
    },
  },
}
</script>