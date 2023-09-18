<template>
  <div class="app-container">
    <AppHeader />

    <main class="app-content">
      <NuxtPage />
    </main>
  </div>
</template>

<script setup lang="ts">
/** ALL META TAGS */
const { title, description } = useAppConfig()
const colorMode = useColorMode()
const color = computed(() => colorMode.value === 'dark' ? '#0f172a' : '#f8fafc')

useHead({
  htmlAttrs: { lang: 'en' },
  link: [
    { rel: 'icon', type: 'image/svg+xml', href: '/logo.svg' }
  ],
  bodyAttrs: {
    class: 'antialiased font-sans text-gray-700 dark:text-gray-200 bg-gray-200 dark:bg-gray-900'
  }
})

useSeoMeta({
  title,
  description,
  themeColor: color,
  ogTitle: title,
  ogDescription: description,
  ogImage: '[og:image]',
  ogUrl: 'https://elexcel.vercel.app/'
})
</script>

<style scoped lang="scss">
.app-container {
  width: 100vw;
  height: 100vh;
  display: flex;
  overflow: hidden;
  flex-direction: column;
}

.app-content {
  flex: 1;
  position: relative;
}
</style>
