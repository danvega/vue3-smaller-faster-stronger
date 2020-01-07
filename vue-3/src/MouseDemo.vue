<template>
  <h1>Use Mouse Demo</h1>
  <p>x: {{ x }} | y: {{ y }}</p>
</template>

<script>
import { useMousePosition } from "./use/useMousePosition";

export default {
  setup() {
    const { x, y } = useMousePosition();
    return { x, y };
  }
};
</script>
