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
      all the mighty warriors
    </h2>
    <div class="grid sm:grid-cols-2 md:grid-cols-3 xl:grid-cols-5 gap-5 pb-8">
      <div
        v-for="(player, index) in players.data"
        :key="index"
        class="rounded-lg grid w-full grid place-items-center"
      >
        <p class="capitalize font-semibold text-2xl text-center">
          {{ player.name }}
        </p>
        <p
          class="
            text-2xl
            font-black
            bg-clip-text bg-gradient-to-br
            from-yellow-400
            to-pink-500
            text-transparent
          "
        >
          {{ player.number }}
        </p>
        <img :src="player.img" alt="" class="w-80 rounded-3xl" />
      </div>
    </div>
  </div>
</template>