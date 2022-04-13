<template>
  <div>
    <v-app-bar
      app
      :color="color"
      :flat="flat"
      dark
      :class="{ expand: flat }"
    >
      <v-toolbar-title>
        <v-img :src="require('@/assets/logo.png')" max-width="50px" />
      </v-toolbar-title>
      <v-spacer />
      <div v-if="!isXs">
        <v-btn text @click="$vuetify.goTo('#home')">
          <span class="mr-2">Home</span>
        </v-btn>
        <v-btn text @click="$vuetify.goTo('#about')">
          <span class="mr-2">About</span>
        </v-btn>
        <v-btn text @click="$vuetify.goTo('#roadmap')">
          <span class="mr-2">Roadmap</span>
        </v-btn>
        <v-btn text @click="$vuetify.goTo('#team')">
          <span class="mr-2">Team</span>
        </v-btn>
        <v-btn text @click="$vuetify.goTo('#faq')">
          <span class="mr-2">FAQ</span>
        </v-btn>
        <v-btn rounded outlined text @click="$vuetify.goTo('#contact')">
          <span class="mr-2">BUY</span>
        </v-btn>
      </div>

      <v-btn
          v-else
          v-for="(icon, i) in social"
          :key="i"
          class="mx-1 white--text"
          :href="icon.link"
          target="_blank"
          icon
        >
          <component :is="icon.component"/>
      </v-btn>
      <v-btn v-if="isXs" rounded outlined text @click="$vuetify.goTo('#contact')">
        <span class="mr-2">BUY</span>
      </v-btn>
    </v-app-bar>
  </div>
</template>

<style scoped>
.v-toolbar {
  transition: 0.6s;
}

.expand {
  height: 80px !important;
  padding-top: 10px;
}
</style>

<script>
import IconTwitter from "./icons/IconTwitter";
import IconDiscord from "./icons/IconDiscord";
import IconTelegram from "./icons/IconTelegram";

export default {
  name: "MainNavigation",
  components: {
    // eslint-disable-next-line vue/no-unused-components
    IconTwitter,
    // eslint-disable-next-line vue/no-unused-components
    IconDiscord,
    // eslint-disable-next-line vue/no-unused-components
    IconTelegram
  },
  data: () => ({
    drawer: null,
    isXs: false,
    items: [
      ["mdi-home-outline", "Home", "#home"],
      ["mdi-information-outline", "About", "#features"],
      ["mdi-download-box-outline", "Roadmap", "#download"],
      ["mdi-currency-usd", "Preços", "#pricing"],
      ["mdi-email-outline", "Contatos", "#contact"],
    ],
    social: [
      {
        component: IconDiscord,
        link: "http://discord.gg/WRVZBaHv9N",
      },
      {
        component: IconTwitter,
        link: "https://mobile.twitter.com/USloths",
      },
      {
        component: IconTelegram,
        link: "http://t.me/UrbanSlothsLou",
      },
    ]
  }),
  props: {
    color: String,
    flat: Boolean,
  },
  methods: {
    onResize() {
      this.isXs = window.innerWidth < 850;
    },
  },

  watch: {
    isXs(value) {
      if (!value) {
        if (this.drawer) {
          this.drawer = false;
        }
      }
    },
  },
  mounted() {
    this.onResize();
    window.addEventListener("resize", this.onResize, { passive: true });
  },
};
</script>
