<template>
  <a v-if="external" :href="external" target="_blank"><p class="inline-block">(?)</p></a>
  <a v-else href="#"><p class="inline-block">(?)</p></a>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    external: String,
  },
  setup() {
    return {};
  },
});
</script>

<style scoped></style>
