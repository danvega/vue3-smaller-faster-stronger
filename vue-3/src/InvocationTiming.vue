<template>
  <h1>Invocation Timing Demo</h1>
  <p>{{ upperCaseMsg }}</p>
</template>

<script>
import { created } from "vue";

export default {
  data() {
    return {
      msg: "Hello, Composition API"
    };
  },
  setup() {
    console.log("setup()");
  },
  beforeCreate() {
    console.log("beforeCreate lifecycle hook");
  },
  created() {
    console.log("created lifecycle hook");
  },
  computed: {
    upperCaseMsg() {
      return this.msg.toUpperCase();
    }
  }
};
</script>

<style>
</style>
