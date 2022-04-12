<template>
  <v-app dark>
    <navigation :color="color" :flat="flat" />
    <v-main class="pt-0">
      <Home />
      <About />
      <Team />
      <Faq />
    </v-main>
    <v-scale-transition>
      <v-btn
        fab
        v-show="fab"
        v-scroll="onScroll"
        dark
        fixed
        bottom
        right
        color="secondary"
        @click="toTop"
      >
        <v-icon>mdi-arrow-up</v-icon>
      </v-btn>
    </v-scale-transition>
    <Footer />
  </v-app>
</template>

<style lang="scss" scoped>
.v-main {
  background-image: url("~@/assets/bgSloth.png");
  background-color: #000000;
  background-attachment: fixed;
  background-position: 20% 20%;
  background-size: 100%;
}
.theme--dark.v-application {
  background-color: #000000 !important;
}
</style>

<script>
import navigation from "./components/MainNavigation";
import Footer from "./components/MainFooter";
import Home from "./components/HomeSection";
import About from "./components/AboutSection";
import Faq from "./components/FaqSection"
// import Roadmap from "./components/MainRoadmap";
import Team from "./components/TeamSection"

export default {
  name: "App",

  components: {
    navigation,
    Footer,
    Home,
    About,
    Team,
    Faq
  },

  data: () => ({
    fab: null,
    color: "",
    flat: null,
  }),

  created() {
    const top = window.pageYOffset || 0;
    if (top <= 60) {
      this.color = "transparent";
      this.flat = true;
    }
  },

  watch: {
    fab(value) {
      if (value) {
        this.color = "secondary";
        this.flat = false;
      } else {
        this.color = "transparent";
        this.flat = true;
      }
    },
  },

  methods: {
    onScroll(e) {
      if (typeof window === "undefined") return;
      const top = window.pageYOffset || e.target.scrollTop || 0;
      this.fab = top > 60;
    },
    toTop() {
      this.$vuetify.goTo(0);
    },
  },
};
</script>
