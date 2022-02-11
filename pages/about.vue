<script>
export default {
  async asyncData({ $content }) {
    const about = await $content('about').fetch()

    return { about }
  },
}
</script>

<template>
  <div>
    <h2
      class="
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
      {{ about.title }}
    </h2>
    <nuxt-content :document="about" class="pt-4" />
  </div>
</template>