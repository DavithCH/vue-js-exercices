<script setup>
import { ref } from "vue";
const counter = ref(0);
setInterval(function () {
  counter.value++;
}, 1000);
</script>

<template>
  <h1>
    Counter
    {{ counter }}
  </h1>
</template>
