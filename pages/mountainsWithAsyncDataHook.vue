<template>
  <v-app>
    <div class="container mx-auto mt-8">
      <MountainCard class="mb-4" v-for="mountain in mountains" :mountain="mountain" :key="mountain.title"/>
    </div>
  </v-app>
</template>
 
<script>
import MountainCard from "/components/MountainCard.vue"
  export default {
    components: {
      MountainCard,
    },
    data: () => ({
      mountains: []
    }),
    async asyncData({ _params }) { 
      const mountains = await fetch("https://api.nuxtjs.dev/mountains").then((res) => res.json());
      return {
        mountains
      }
    }
  }
</script>
<style>
.progressWrapper {
    margin: auto auto;
}
</style>