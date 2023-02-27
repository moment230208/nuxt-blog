<script setup lang="tsx">
const { description, title, navlinks } = useAppConfig()
</script>

<template>
  <header class="w-full max-w-5xl px-3 flex flex-row justify-between items-center h-[60px] mx-auto">
    <div class="flex flex-row items-center">
      <NuxtLink class='flex items-center' href="/">
        <nuxt-img
          src="/logo.jpg"
          alt="moment"
          :width="40"
          :height="40"
          class="object-cover"
        />
        <span class="mx-2 font-extrablog text-lg">
          {{ title }}
        </span>
      </NuxtLink>
    </div>
    <nav class="flex gap-5">
      <NuxtLink 
        v-for="nav in navlinks"
        :key="nav.link"
        :href="nav.link">
        {{ nav.title }}
      </NuxtLink>
      <!-- {
        navlinks.map((nav) => (
          <Link className={'mr-5'} href={nav.link} key={nav.title}>
            {nav.title}
          </Link>
        ))
      } -->
    </nav>
  </header>
</template>