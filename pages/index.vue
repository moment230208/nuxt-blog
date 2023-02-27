<script setup lang="tsx">
const { description, title } = useAppConfig()
</script>

<template>
  <div class="w-full relative h-[400px] overflow-hidden flex items-center justify-center">
    <nuxt-img
      src="/home.jpg"
      alt="대표 이미지"
      :width="1920"
      :height="1280"
      class="object-cover w-full min-w-[1920px] rounded-5xl absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2"
    />
    <span class="font-extrabold italic text-white text-3xl md:text-5xl relative drop-shadow-2xl">
      {{ title }}
    </span>
  </div>
  <div class="max-w-5xl px-3 w-full mx-auto my-20">
    <h1 class="text-5xl font-extrabold mb-12">Recent Blog Post</h1>
    <div class="flex flex-col gap-10">
      <ContentList path="/blog" v-slot="{ list }">
        <NuxtLink 
          v-for="article in list.slice(0, 5)"
          :key="article._path"
          :href="article._path">
          <h2 class="font-bold text-2xl mb-3">{{ article.title }}</h2>
          <p class="font-regular">{{ article.description }}</p>
        </NuxtLink>
      </ContentList>
    </div>
    <!-- <RecentPosts posts={posts} /> -->
  </div>
</template>