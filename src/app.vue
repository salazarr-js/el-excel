<template>
  <div class="min-h-screen flex flex-col">
    <Header />

    <main class="relative flex-1 px-4 md:px-8 py-4">
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
    class: 'antialiased font-sans text-gray-700 dark:text-gray-200 bg-gray-100 dark:bg-gray-900'
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

<style scoped lang="scss"></style>
