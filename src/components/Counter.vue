<script setup>
import { ref } from "vue";
const counter = ref(0);
setInterval(function () {
  counter.value++;
}, 1000);

const resetButton = () => {
  counter.value = 0;
};
</script>

<template>
  <h1>
    Counter
    {{ counter }}
  </h1>
  <button @click="resetButton">reset counter</button>
</template>
