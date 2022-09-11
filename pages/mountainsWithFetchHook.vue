<template>
  <v-app>
    <span v-if="$fetchState.pending" class="progressWrapper">
      <v-progress-circular
        :size="70"
        :width="7"
        color="purple"
        indeterminate
      />
      <p class="mt-2 ml-1 purple--text">
        Loading
      </p>
    </span>
    <span v-else-if="$fetchState.error" class="progressWrapper">
      <p class="mt-2 ml-1 purple--text">
        An error occurred :(
      </p>
    </span>
    <div v-else>
      <div class="container mx-auto mt-8">
        <MountainCard class="mb-4" v-for="mountain in mountains" :mountain="mountain" :key="mountain.title"/>
      </div>
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
    async fetch() { 
      //throw new Error("Uncomment to see failure case");
      this.mountains = await fetch("https://api.nuxtjs.dev/mountains").then((res) => res.json());
      console.log("this.mountains: ", this.mountains);
    }
  }
</script>
<style>
.progressWrapper {
    margin: auto auto;
}
</style>