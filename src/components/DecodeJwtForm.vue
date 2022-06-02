<script setup>
import { ref } from "vue";
import * as jose from "jose";
const token = ref("");
const result = ref({});
const decodeToken = () => {
  result.value = jose.decodeJwt(token.value);
};
</script>

<template>
  <textarea
    id=""
    cols="30"
    rows="10"
    v-model="token"
    placeholder="Insert a token here ..."
  >
  </textarea>
  <button @click="decodeToken">Decode this token</button>

  <h3>Decoded token is :</h3>
  <p>{{ result }}</p>
</template>
