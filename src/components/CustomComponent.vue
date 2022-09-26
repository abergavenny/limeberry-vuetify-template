<script setup lang="ts">
import { onMounted, ref, watch, watchEffect } from "vue";
import ListComponent from "./ListComponent.vue";

const props = defineProps(["url"]);

const resourceUrl = ref("");

// watchEffect runs on init
watchEffect(() => {
  resourceUrl.value = props.url;
});

// watch runs lazily
watch(
  () => props.url,
  (curr, prev) => {
    console.log("DEBUG", curr, prev);
  }
);

onMounted(() => {});
</script>

<template>
  <v-container>
    <div>Vuetify Container</div>
    <div>
      {{ resourceUrl }}
    </div>
    <div>
      <v-text-field label="Resource URL" />
    </div>
    <ListComponent :data="null" />
  </v-container>
</template>
