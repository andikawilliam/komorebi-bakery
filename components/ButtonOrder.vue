<template>
  <a :href="whatsappLink">
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
  },
  data() {
    return {
      contact: {}
    }
  },
  computed: {
    whatsappLink: function() {
      return "http://wa.me/" + this.contact.whatsapp
    }
  },
  async fetch() {
    this.contact = await this.$content("contact").fetch();
  }
  
}
</script>