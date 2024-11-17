<script setup>
import { ref } from 'vue';
const valueN = ref(0)
const piAproximation = ref(0)

function calculatePi() {
    piAproximation.value = 0
    for (let i = 0; i < valueN.value; i++) {
        piAproximation.value += (4 * ((-1) ** i) / (2 * i + 1));
    }
}
</script>
<template>
<form @submit.prevent="calculatePi()">
    <div class="calculator-container">
        <h1>GregoryLeibnizPi</h1>
        <label>n:</label>
        <input v-model="valueN" type="number" />
        <label>piAproximation:</label>
        <input v-model="piAproximation" type="number" readonly />
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