<template>
  <div
    class="h-screen bg-shadow bg-center bg-cover text-gray-200 relative"
    :style="{
      'background-image': `url(${ home.background })`
    }"
  >
    <div class="flex justify-center items-center h-screen">
      <div class="w-4/5 lg:w-2/3">
        <div
          class="text-center text-4xl sm:text-6xl lg:text-6xl xl:text-7xl font-black tracking-wide line-height p-2 sm:p-4"
        >
          <p>
            {{ home.headline }}
            <span class="text-red-500 opacity-80">
              {{ home.highlight }}
            </span>
          </p>
        </div>
        <div class="flex justify-center text-lg">
          <NuxtLink to="/products">
            <button class="button bg-white mx-4">
              Menu
            </button>
          </NuxtLink>
          <ButtonOrder />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { InstagramIcon, WhatsAppIcon } from 'vue-simple-icons'

export default {
  transition: 'page',
  async asyncData({ $content }) {
    const home = await $content("home").fetch();

    return {
      home,
    };
  }
}
</script>

<style>
</style>
