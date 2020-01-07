<template>
  <h1>Lifecycle Hooks in Setup</h1>
  {{ count }}
</template>

<script>
import { ref, watch } from "vue";

export default {
  setup() {
    const count = ref(0);

    watch(() => {
      console.log(`watching count: ${count.value}`);
    });

    setInterval(() => {
      count.value++;
    }, 1000);

    return { count };
  }
};
</script>

<style>
</style>
