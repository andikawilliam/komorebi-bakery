<template>
  <div
    class="h-screen bg-shadow bg-center bg-cover text-gray-200 relative"
    :style="{
      'background-image': `url(${require('~/assets/img/komorebi-2.jpg')})`
    }"
  >
    <div class="flex justify-center items-center h-screen">
      <div class="w-4/5 lg:w-2/3">
        <div class="text-center text-4xl sm:text-6xl lg:text-6xl xl:text-7xl font-black line-height p-2 sm:p-4">
          Our Specialties
        </div>
        <div
          class="w-4/5 mx-auto grid grid-cols-2 gap-4 sm:gap-24 text-lg font-semibold text-center mt-6"
        >
          <div>
            <img 
              class="transition duration-300 transform hover:-translate-y-3 rounded-full"
              src="~/assets/img/cookies-1.jpg"
              alt="cookies"
            />
            <p class="mt-4">Cookies</p>
          </div>
          <div>
            <img 
              class="transition duration-300 transform hover:-translate-y-3 rounded-full"
              src="~/assets/img/banoffee-1.png"
              alt="banoffee"
            />
            <p class="mt-4">Banoffee</p>
          </div>
        </div>
        <div class="flex justify-center mt-8">
          <ButtonOrder />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>
