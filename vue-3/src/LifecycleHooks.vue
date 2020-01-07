<template>
  <h1>Lifecycle Hooks in Setup</h1>
  {{ count }}
</template>

<script>
import { ref, onBeforeMount, onMounted, onUpdated } from "vue";

export default {
  setup() {
    const count = ref(0);

    onBeforeMount(() => {
      console.log("onBeforeMount() called...");
    });
    onMounted(() => {
      console.log("onMounted() called...");
    });
    onUpdated(() => {
      console.log("onUpdated() called...");
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
