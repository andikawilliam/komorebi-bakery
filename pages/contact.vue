<template>
  <div class="flex items-center h-screen text-gray-200 bg-contact relative">
    <div class="h-full image-shadow overflow-hidden">
      <img
        class="object-cover h-full w-full mx-0 object-top lg:w-auto lg:h-screen"
        src="~/assets/img/komorebi-vertical.jpg"
      />
    </div>
    <div class="absolute px-6 sm:pl-12 lg:static lg:px-8 xl:pl-16">
      <h1 class="text-3xl sm:text-5xl xl:text-6xl font-black">Contact</h1>
      <div class="mt-2 lg:mt-6 text-lg sm:text-xl">
        <p class="mb-2 font-semibold text-red-500">Komorebi Bakery<p/>
        <p>
          For order and more info contact us on:
        </p>
        <a :href="instagramLink">
          <p class="hover:opacity-60">
            <instagram-icon size="1x" class="fill-current inline mr-1" />
            Instagram: @{{ contact.instagram }}
          </p>
        </a>
        <a :href="whatsappLink">
          <p class="hover:opacity-60 mb-4" >
            <whats-app-icon size="1x" class="fill-current inline mr-1" />
            Whatsapp: +{{ contact.whatsapp }}
          </p>
        </a>
        <ButtonOrder />
      </div>
    </div>
    <div class="hidden absolute lg:block right-0 bottom-0">
      <p class="text-center text-gray px-2">I know you want me..</p>
      <img class="" src="~/assets/img/cookie.png"/>
    </div>
  </div>
</template>

<script>
import { InstagramIcon ,WhatsAppIcon } from 'vue-simple-icons'

export default {
  components: {
    InstagramIcon, WhatsAppIcon
  },

  computed: {
    instagramLink: function() {
      return "https://www.instagram.com/" + this.contact.instagram
    },
    whatsappLink: function() {
      return "http://wa.me/" + this.contact.whatsapp
    }
  },

  async asyncData({ $content }) {
    const contact = await $content("contact").fetch();

    return {
      contact,
    };
  }
}
</script>

<style scoped>
.bg-contact {
  background-color: #252525;
}

@media (max-width: 1023px) { 
  .image-shadow:after {
    content: '\A';
    position: absolute;
    width: 100%;
    height: 100%;
    top:0;
    left:0;
    background:rgba(0,0,0,0.5);
  }
}

</style>
