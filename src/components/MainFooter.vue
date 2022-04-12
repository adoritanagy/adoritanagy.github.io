<template>
  <v-footer dark padless>
    <v-card flat tile class="secondary white--text text-center">
      <v-card-text>
        <v-btn
          v-for="(icon, i) in icons"
          :key="i"
          class="mx-4 white--text"
          :href="icon.link"
          target="_blank"
          icon
        >
          <component :is="icon.component"/>
        </v-btn>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        <div class="d-flex align-center justify-center">
          <IconElrond class="mr-4"/>
          <div>
            <span>Made in Elrond with <v-icon color="#ff385c">mdi-heart</v-icon></span>
          </div>
        </div>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ copyright }}
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<style scoped>
.v-card {
  width: 100%;
}
</style>

<script>
import IconTwitter from "./icons/IconTwitter";
import IconDiscord from "./icons/IconDiscord";
import IconTelegram from "./icons/IconTelegram";
import IconElrond from "./icons/IconElrond";

export default {
  name: "MainFooter",
  components: {
    // eslint-disable-next-line vue/no-unused-components
    IconTwitter,
    // eslint-disable-next-line vue/no-unused-components
    IconDiscord,
    // eslint-disable-next-line vue/no-unused-components
    IconTelegram,
    IconElrond
  },
  data: () => ({
    icons: [
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
  computed: {
    copyright() {
      return `©${new Date().getFullYear()} - Urban Sloth. All rights reserved`
    }
  }
};
</script>
