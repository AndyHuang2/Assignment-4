<script setup>
import AsymptoteFinder from './components/AsymptoteFinder.vue';
import CosLaw from './components/CosLaw.vue';
import GregoryLeibnizPi from './components/GregoryLeibnizPi.vue';
</script>

<template>
  <div class="app-container">
    <div class="calculators">
      <CosLaw />
      <AsymptoteFinder />
      <GregoryLeibnizPi />
    </div>
  </div>
</template>

<style scoped>
.app-container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 150px; /* Add padding to prevent cutting off content */
  height: 700px; /* Full viewport height */
  box-sizing: border-box; /* Ensure padding doesn't cause overflow */
}

.calculators {
  display: grid;
  grid-template-columns: 1fr 1fr; /* Two columns in the top row */
  grid-template-rows: auto auto; /* Two rows */
  gap: 20px; /* Space between items */
  justify-items: center; /* Center items horizontally */
  align-items: center; /* Center items vertically */
}
</style>