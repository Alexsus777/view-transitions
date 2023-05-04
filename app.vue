<template>
  <div>
    <header class="w-full bg-black p-2 flex gap-4 items-center main-header">
      <nuxt-link class="flex items-center" to="/">
        <div v-if="route.fullPath !== '/'" class="text-white">Go to</div>
        <p class="text-white mx-4 main-header-text" >Root</p>
      </nuxt-link>
      <nuxt-link class="text-white" to="/fade">fade</nuxt-link>
      <nuxt-link class="text-white" to="/slide">slide</nuxt-link>
      <nuxt-link class="text-white" to="/gallery">gallery</nuxt-link>
    </header>
    <div>
      <NuxtPage />
    </div>
  </div>
</template>

<script lang="ts" setup>
const back = ref<HTMLDivElement>()

const route = useRoute()
</script>


<style>
.main-header {
  view-transition-name: main-header;
  contain: layout;
}

.main-header-text {
  view-transition-name: main-header-text;
  contain: layout;
  width: fit-content;
}

.big-card {
  position: absolute;
  width: 100%;
  height: 100%;
}

.base-card {
  position: static;
  width: 150px;
  height: auto;
}
</style>