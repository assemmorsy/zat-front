<template>
  <div dir="rtl" lang="ar"
    class="flex flex-col min-h-screen bg-white text-slate-800 dark:bg-slate-800 dark:text-slate-50">
    <Navbar />
    <main class="p-2 grow items-start w-full relative">
      <NuxtPage />
      <UNotifications />

    </main>
    <AppFooter />
  </div>
</template>

<script setup lang="ts">
const client = useStrapiClient()

onMounted(() => {
  client(`/website-visits-counter/add-one`, { method: 'POST' })
})
</script>
