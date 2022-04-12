<template>
  <section id="about" class="text-center py-12">
    <h2 class="mb-12">
      ABOUT
    </h2>
    <p>
      The Urban Sloths are a collection of 5000 NFTs generated at random from traits hand drawn by our artist.
    </p>
    <p>
      The sloths moved from their tropical forest to the urban jungle and are now attempting to adapt. Despite moving only 36 meters each day and sleeping for 15 hours, they have managed to find regular jobs.
    </p>
    <p class="mb-0">Check out the Roadmap below, we have a bright future ahead of us!</p>
  </section>
</template>

<script>
export default {
  data(){
    return {
      publicPath: process.env.BASE_URL,
    }
  }
}
</script>

<style scoped>
#about {
  background-color: #000000;
}
</style>
