<template>
  <div>
    <div class="absolute flex justify-center items-center h-screen w-full">
      <div
        class="text-center text-4xl font-black main-header text-gray-300 opacity-50"
      >
        <p>木漏れ日</p>
        <p class="text-2xl mt-2">komorebi bakery</p>
      </div>
    </div>
    <TheNav />
    <Nuxt />
  </div>
</template>

<style>
html {
  font-family:
    'Noto Sans JP',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

body {
  background-color: #252525;
  background-size: 60px 60px;
  background-image:
    linear-gradient(to right, rgba(128, 128, 128, 0.6) .2px, transparent .5px),
    linear-gradient(to bottom, rgba(128, 128, 128, 0.6) .2px, transparent .5px);
}
</style>
