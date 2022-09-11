<template>
  <v-app>
    <v-container mt-2>
      <v-row class="mb-2" align="center" justify="center"> 
        <div class="indigo--text font-weight-bold">
            {{mountain.title}}
        </div>
      </v-row>
      <v-row align="center" justify="center">
        <v-img
        class="rounded"
        max-height="300"
        max-width="300"
        :src="mountain.image"
        :alt="mountain.title"
        />
      </v-row>
      <v-row>
        <div class="ml-4 mt-2"  align="center" justify="center">
          <div class="gray--text">
            <span class="font-weight-bold">Continent:</span> {{ mountain.continent }}
          </div>
          <p class="mt-2 gray--text">
            <span class="font-weight-bold">Description:</span> {{ mountain.description }}
          </p>
        </div>
      </v-row>
    </v-container>
  </v-app>
</template>
 
<script>
  export default {
    data: () => ({
      mountain: []
    }),
    async asyncData({ params }) {
      const mountain = await fetch(`https://api.nuxtjs.dev/mountains/${params.mountain}`).then((res) => res.json());
      return {
        mountain
      }
    }
  }
</script>