<template>
  <div class="mt-8 space-y-6">
    <header class="space-y-4">
      <div class="flex justify-between items-center">
        <h1 class="text-3xl mb-0 text-gray-700 dark:text-gray-300">人物</h1>
        <the-link-button href="https://github.com/overtrue/laravel.xyz/edit/master/content/packages.json" class="flex items-center space-x-2">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
          </svg>
          <span>推荐更多人选</span>
        </the-link-button>
      </div>
      <div class="text-gray-500 dark:text-neutral-400">关注他们，学习和模仿。</div>
    </header>
    <div class="grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 content-center gap-6 w-full">
      <star-card v-for="star of stars.body" :star="star" class="mx-auto w-full" :key="star.name"></star-card>
    </div>
  </div>
</template>

<script setup>
const { data: stars } = await useAsyncData('stars', () => queryContent('/compiled/stars').findOne())
</script>
