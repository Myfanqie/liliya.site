<template>
  <NavBar />
  <main class="px-7 py-10">
    <router-view />
    <Footer />
  </main>
</template>

<script setup lang="ts">
useHead({
  meta: [
    { property: 'og:title', content: 'Liliya' },
    { property: 'og:image', content: 'https://avatars.githubusercontent.com/u/50412437?s=400&u=308833608ef36baa60f51d695d18fc6159cfc6c5&v=4' },
    { name: 'description', content: 'Liliya\'s Portfolio' },
    // { name: 'twitter:card', content: 'summary' },
    // { name: 'twitter:creator', content: '@antfu7' },
  ],
})
</script>
