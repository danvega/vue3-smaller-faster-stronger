<template>
  <!-- no need to use msg.value in templates, you will have to in the setup method though -->
  <h1>{{ msg }}</h1>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const msg = ref("Hello, Vue 3!");
    return { msg };
  }
};
</script>

<style scoped>
</style>
