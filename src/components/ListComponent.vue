<script setup lang="ts">
defineProps(["data"]);
</script>

<template>
  <v-container>
    <div v-for="element in data" :key="element"></div>
  </v-container>
</template>
