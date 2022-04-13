<template>
  <section id="home" class="home-section">
    <v-parallax dark :height="height" class="parallax">
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row align="end" justify="end">
            <v-col cols="12" md="8" xl="8" sm="8" xs="12" class="text-right">
              <h1 class="font-weight-bold mb-4">COME TO THE SLOTH SIDE, WE HAVE NAPS</h1>
              <v-btn
                rounded
                outlined
                large
                dark
                @click="$vuetify.goTo('#about')"
                class="mt-5"
              >
                LEARN MORE
                <v-icon class="ml-2">mdi-arrow-down</v-icon>
              </v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
      <div class="svg-border-waves text-white">
        <v-img :src="require('@/assets/borderWaves.svg')" />
      </div>
    </v-parallax>
  </section>
</template>

<script>
export default {
  name: "HomeSection",
  data() {
    return {
    };
  },
  computed: {
      height () {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': return 400
          case 'sm': return 400
          case 'md': return 500
          case 'lg': return 600
          case 'xl': return 700
          default: return 700
        }
      }
    }
};
</script>

<style lang="scss">

</style>

<style lang="scss">
@import '~vuetify/src/styles/styles.sass';

.home-section {
  h1 {
    font-size: 50px;
  }
}

@media #{map-get($display-breakpoints, 'md-and-down')} {
  .home-section {
    h1 {
      font-size: 40px;
    }
  }
}

@media #{map-get($display-breakpoints, 'sm-and-down')} {
  .home-section {
    h1 {
      font-size: 30px;
    }
  }
}

.svg-border-waves .v-image {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3rem;
  width: 100%;
  overflow: hidden;
}

#home {
  z-index: 0;
}
.svg-border-waves img {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  margin-bottom: -2px;
  z-index: -1;
}

.card {
  min-height: 300px;
  padding: 10px;
  transition: 0.5s ease-out;
}

.card .v-image {
  margin-bottom: 15px;
  transition: 0.75s;
}

.card h1 {
  margin-bottom: 10px;
}

.zoom-efect {
  transform: scale(1.1);
}

.up {
  transform: translateY(-20px);
  transition: 0.5s ease-out;
}
</style>

<style>
section {
  position: relative;
}
</style>
