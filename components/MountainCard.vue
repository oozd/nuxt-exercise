<template>
  <div class="d-flex">
    <div>
      <v-img
      class="rounded"
      width="150px"
      :src="mountain.image"
      :alt="mountain.title"
      />
    </div>
    <div class="ml-4">
      <NuxtLink class="mt-2 indigo--text hover:underline" :to="mountain.slug">
        <span class="font-weight-bold">Title:</span> {{ mountain.title }}
      </NuxtLink>
      <div class="gray--text">
        <span class="font-weight-bold">Continent:</span> {{ mountain.continent }}
      </div>
      <p class="gray--text">
        <span class="font-weight-bold">Description:</span> {{ mountain.description }}
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      mountain: {
        type: Object,
        default: () => {}
      }
    }
  }
</script>

<style> 
.v-img {
  height: 10px;
  object-fit: cover;
}
</style>