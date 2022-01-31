<script>
export default {
  async asyncData({ $content }) {
    const community = await $content('community').fetch()

    return { community }
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
      Our community section
    </h2>
    <nuxt-child />
  </div>
</template>