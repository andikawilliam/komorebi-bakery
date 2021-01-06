<template>
  <a href="http://wa.me/6285287276767">
    <button class="button bg-red-500">
      <whats-app-icon size="1x" class="fill-current inline mr-1" />
      Order Now
    </button>
  </a>
</template>

<script>
import { WhatsAppIcon } from 'vue-simple-icons'

export default {
  components: {
    WhatsAppIcon
  }
}
</script>