<template>
  <div class="grid text-center">
    <h1 class="text-3xl font-bold text-center pt-6 text-red-600">
      hello world!! it always the browser loool okay we can continue
    </h1>
    <p class="text-4xl font-bold text-blue-300">using firefox for dev</p>
    <ul class="grid grid-auto-row gap-3 pt-4">
      <li class="text-purple-300 text-xl">
        component what the hell, new content, okay this is fine and quick now
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const fixtures = await $content('fixtures').fetch()

    return { fixtures }
  },
}
</script>
