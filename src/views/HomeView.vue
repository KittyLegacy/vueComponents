<script setup>
</script>

<template>

  <main>
    <router-link to="/alerts" custom v-slot="{ navigate }">
      <button @click="navigate" type="button" class="btn btn-primary btn-lg mr-6">Alerts</button>
    </router-link>

    <router-link to="/buttons" custom v-slot="{ navigate }">
      <button @click="navigate" type="button" class="btn btn-primary btn-lg mr-6">Buttons</button>
    </router-link>
  </main>

</template>

<style scoped>
  .mr-6{
    margin-right: 6px;
  }
</style>
