<template>
  <section id="about" class="text-center about-section py-12 sm:py-5">
    <div v-if="!$vuetify.breakpoint.mobile" class="max-width-section">
      <h2 class="mb-6">
        ABOUT
      </h2>
      <BaseDivider class="divider mb-12"/>
      <p>
        The Urban Sloths are a collection of 5000 NFTs generated at random from traits hand drawn by our artist.
      </p>
      <p>
        The sloths moved from their tropical forest to the urban jungle and are now attempting to adapt.
      </p>
      <p>Despite moving only 36 meters each day and sleeping for 15 hours, they have managed to find regular jobs.</p>
      <p>Check out the Roadmap below, we have a bright future ahead of us!</p>
      <v-container fluid>
        <v-row align="center" justify="center">
          <v-col cols="12">
            <v-row align="center" justify="center">
              <v-col cols="3" lg="3" sm="3" xs="6" class="white--text text-left">
                <v-img class="avatar" :src="require('@/assets/sloth2.jpeg')"/>
              </v-col>
              <v-col cols="3" lg="3" sm="3" xs="6" class="white--text text-left">
                <v-img class="avatar" :src="require('@/assets/sloth3.jpeg')"/>
              </v-col>
              <v-col cols="3" lg="3" sm="3" xs="6" class="white--text text-left">
                <v-img class="avatar" :src="require('@/assets/sloth4.jpeg')"/>
              </v-col>
              <v-col cols="3" lg="3" sm="3" xs="6"  class="white--text text-left">
                <v-img class="avatar" :src="require('@/assets/sloth5.jpeg')"/>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </div>

    <div v-else class="max-width-section">
      <h2 class="mb-6">
        ABOUT
      </h2>
      <BaseDivider class="divider mb-12"/>
      <v-container fluid>
        <v-row align="start" justify="center">
          <v-col cols="12" sm="6">
            <p>
              The Urban Sloths are a collection of 5000 NFTs generated at random from traits hand drawn by our artist.
            </p>
            <p>
              The sloths moved from their tropical forest to the urban jungle and are now attempting to adapt.
            </p>
            <p>Despite moving only 36 meters each day and sleeping for 15 hours, they have managed to find regular jobs.</p>
            <p>Check out the Roadmap below, we have a bright future ahead of us!</p>
          </v-col>
          <v-col cols="10" sm="6">
            <v-row align="center" justify="center">
              <v-col cols="6" class="white--text text-left">
                <v-img class="avatar" :src="require('@/assets/sloth2.jpeg')"/>
              </v-col>
              <v-col cols="6" class="white--text text-left">
                <v-img class="avatar" :src="require('@/assets/sloth3.jpeg')"/>
              </v-col>
              <v-col cols="6" class="white--text text-left">
                <v-img class="avatar" :src="require('@/assets/sloth4.jpeg')"/>
              </v-col>
              <v-col cols="6" class="white--text text-left">
                <v-img class="avatar" :src="require('@/assets/sloth5.jpeg')"/>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </section>
</template>

<script>
import BaseDivider from "@/components/BaseDivider";

export default {
  name: "AboutSection",
  components: {
    BaseDivider
  },
  data(){
    return {
      publicPath: process.env.BASE_URL,
    }
  }
}
</script>

<style lang="scss">
.about-section  {
  background-color: #000000;

  .max-width-section {
    margin: 0 auto;
    max-width: 1000px;
    padding-left: 20px;
    padding-right: 20px;
  }

  .divider {
    max-width: 100px;
    margin-left: auto;
    margin-right: auto;
  }

  .avatar {
    border-radius: 4px;
  }
}
</style>
