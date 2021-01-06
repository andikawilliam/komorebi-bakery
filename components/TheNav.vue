<template>
  <div class="absolute z-10 flex justify-between w-full">
    <NuxtLink to="/" class="text-gray-200 bg-red-900 bg-opacity-50 p-2 m-2 sm:m-4">
      <p class="sm:text-lg lg:text-2xl">
        KOMOREBI<span class="font-bold"> BAKERY</span>
      </p>
      <p class="text-xs sm:text-sm lg:text-lg">
        木漏れ日
      </p>
    </NuxtLink>
    <div 
      class="absolute z-30 nav-burger sm:hidden"
      v-on:click="activeSidebar = !activeSidebar"
    >
      <span 
        class="burger-line"
        id="top-bun"
        v-bind:class="{ 'transform rotate-45 translate-y-1.5' : activeSidebar}"
      />
      <span 
        class="burger-line"
        id="bot-bun"
        v-bind:class="{ 'transform -rotate-45 -translate-y-2' : activeSidebar}"
      />
    </div>
    <div
      class="sidebar desktopbar"
      v-bind:class="[ activeSidebar ? 'w-full' : 'w-0' ]"
    >
      <div class="text-gray-200 text-3xl sm:text-lg sm:flex">
        <NuxtLink
          class="navline block mx-8 my-4 sm:my-0"
          v-for="page in pages"
          v-bind:key="page.name"
          v-bind:to="page.route"
        >
          <p
            class="capitalize" 
            v-on:click="activeSidebar = false">
            {{ page.name }}
          </p>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeSidebar: false,
      pages: [
        { name: "home", route: "/" },
        { name: "products", route: "/products" },
        { name: "contact", route: "/contact" },
      ]
    }
  }

}
</script>

<style>
.nav-burger {
  @apply fixed z-10 top-6 right-6 w-8 h-6 cursor-pointer;
}

.burger-line {
  @apply block absolute left-0 h-1 w-full bg-gray-200 transition duration-200 ;
}

#top-bun {
	top: 0;
	margin-top: 3px;
}
#bot-bun {
	bottom: 0;
	margin-bottom: 3px;
}

.sidebar {
  @apply absolute transition-width h-screen bg-red-900 bg-opacity-80 overflow-hidden right-0 flex items-center;
}

@screen sm {
  .desktopbar {
    @apply py-6 static bg-transparent h-auto w-auto block;
  }
}

.transition-width {
  transition: width;
  transition-duration: .5s;
}

.navline {
  text-decoration: none;
  position: relative;
}

.navline::after {
  content: '';
  position: absolute;
  top: 50%;
  width: 0;
  left: 0;
  height: 8%;
  background: currentColor;
  transition: width 0.25s ease;
}

.navline:hover::after {
  width: 100%;
}

</style>
