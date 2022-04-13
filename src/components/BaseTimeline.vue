<template>
  <v-timeline 
      :dense="$vuetify.breakpoint.mobile"
      :clipped="$vuetify.breakpoint.mobile"
      class="base-timeline" dark>
    <v-timeline-item
      v-for="(item, i) in items"
      :key="i"
      :large="!$vuetify.breakpoint.mobile"
    >
      <template v-slot:icon>
        <v-avatar>
          <img :src="require('@/assets/logo.png')">
        </v-avatar>
      </template>
      <template v-if="!$vuetify.breakpoint.mobile" v-slot:opposite>
        <span>{{item.quote}}</span>
      </template>
      <v-card class="elevation-2">
        <v-card-title color="primary">
          {{item.title}}
        </v-card-title>
        <v-card-text class="text-left">{{ item.description }}</v-card-text>
      </v-card>
    </v-timeline-item>
  </v-timeline>
</template>
<script>
export default {
    name: "BaseTimeline",
    props: {
        items: {
            type: Array,
            required: true
        }
    }
}
</script>
<style lang="scss">
.base-timeline {
  .v-card .v-card__title {
    color: #f7c21a;
  }
}
</style>