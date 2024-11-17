<script setup>
import { ref } from 'vue';

const aSide = ref(0);
const bSide = ref(0);
const angleC = ref(0);
const cSide = ref(0)
function Coslawcalculator() {
    const angleInRadians = (angleC.value * Math.PI) / 180;
    cSide.value = Math.sqrt(
        aSide.value * aSide.value + bSide.value * bSide.value - (2 * aSide.value * bSide.value * Math.cos(angleInRadians)));
}
</script>

<template>
<form @submit.prevent="Coslawcalculator()">
    <div class="calculator-container">
        <h1>Coslaw</h1>
        <label>a:</label>
        <input v-model="aSide" type = "number"/>
        <label>b:</label>
        <input v-model="bSide" type = "number"/>
        <label>C:</label>
        <input v-model="angleC" type = "number"/>
        <label>c:</label>
        <input v-model="cSide" type = "number" readonly/>
        <input type="submit" value="Calculate" />
    </div>  
 </form>

</template>

<style scoped>
.calculator-container {
  background-color: #1e1e1e;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
  padding: 20px;
  width: 300px;
  margin: 0 auto;
  text-align: center;
  font-family: Arial, sans-serif;
}

h1 {
  font-size: 24px;
  color: #ffffff;
  margin-bottom: 20px;
  font-weight: 600;
}

label {
  display: block;
  margin: 10px 0 5px;
  font-size: 14px;
  color: #bbb;
}

input[type="number"],
input[readonly],
input[type="submit"] {
  font-size: 16px;
  padding: 10px;
  border-radius: 8px;
  box-sizing: border-box;
  width: 100%;
  transition: all 0.3s ease-in-out;
  margin-bottom: 15px;
}

input[type="number"],
input[readonly] {
  border: 1px solid #445;
  background-color: #333;
  color: #fff;
}

input[type="number"]:focus {
  border-color: #007bff;
  box-shadow: 0 0 8px rgba(0, 123, 255, 0.3);
  outline: none;
}

input[readonly] {
  background-color: #444;
  color: #aaa;
}

input[readonly]:focus {
  border-color: #444;
  box-shadow: none;
}

input[type="submit"] {
  background-color: #007bff;
  color: white;
  border: none;
  cursor: pointer;
  font-weight: 600;
}

input[type="submit"]:hover {
  background-color: #0056b3;
}
</style>