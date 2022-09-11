<template>
  <div>
    <v-app>
      <v-row
        align="center"
        justify="space-around"
      >
        <v-btn
          color="primary"
          elevation="10"
          @click="redirectToFetchHook()"
        >Use Fetch Hook
        </v-btn>
        <v-divider vertical />
        <v-btn
          color="primary"
          elevation="10"
          @click="redirectToAsyncDataHook()"
        >Use Async Data Hook
        </v-btn>
      </v-row>
    </v-app>
  </div>
</template>

<script>

export default {
  methods: {
    redirectToFetchHook() {
      this.$router.push("/mountainsWithFetchHook")
    },
    redirectToAsyncDataHook() {
      this.$router.push("/mountainsWithAsyncDataHook")
    }
  }
}
</script>
