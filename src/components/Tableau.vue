<script setup>
import { ref } from "vue";

const tableau = ref([{ id: 1, nom: "chhung", prenom: "davith" }]);
const nom = ref("");
const prenom = ref("");
const handleSubmit = () => {
  let timestamp = new Date().getUTCMilliseconds();
  tableau.value.push({ id: timestamp, nom, prenom });
};
const handleDelelte = (id) => {
  console.log(id);
  tableau.value = tableau.value.filter((el) => el.id !== id);
};
</script>

<template>
  <h3>mon list:</h3>
  <ul v-for="element in tableau" :key="element.id">
    <span @click="handleDelelte(element.id)"
      ><li>{{ element.nom }} {{ element.prenom }}</li></span
    >
  </ul>
  <hr />

  <input type="text" v-model="nom" />
  <input type="text" v-model="prenom" />
  <button @click="handleSubmit">Ajouter</button>
</template>
