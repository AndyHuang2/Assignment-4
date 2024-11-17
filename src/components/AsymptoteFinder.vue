<script setup>
import { ref } from 'vue';

const mValue = ref(0);
const nValue = ref(0);
const asymptoteType = ref(0);
function Asymptotecalculator() {
    if (mValue.value === nValue.value) {
        asymptoteType.value = "The asymptote is horizontal";
    } else if (nValue.value > mValue.value) {
        asymptoteType.value = "The asymptote is the x-axis";
    } else {
        const Difference = mValue.value - nValue.value;
        switch (Difference) {
            case 1:
            asymptoteType.value = "The asymptote is Linear";
                break;
            case 2:
            asymptoteType.value = "The asymptote is Quadratic";
                break;
            case 3:
            asymptoteType.value = "The asymptote is Cubic";
                break;
            case 4:
            asymptoteType.value = "The asymptote is Quartic";
                break;
            case 5:
            asymptoteType.value = "The asymptote is Quintic";
                break;
            case 6:
            asymptoteType.value = "The asymptote is Sextic";
                break;
            case 7:
            asymptoteType.value = "The asymptote is Septic";
                break;
            case 8:
            asymptoteType.value = "The asymptote is Octic";
                break;
            case 9:
            asymptoteType.value = "The asymptote is Nonic";
                break;
            case 10:
            asymptoteType.value = "The asymptote is Decic";
        }
    }

}
</script>

<template>
<form @submit.prevent="Asymptotecalculator()">
    <div class="calculator-container">
        <h1>AsymptoteFinder</h1>
        <label>m:</label>
        <input v-model="mValue" type = "number"/>
        <label>n:</label>
        <input v-model="nValue" type = "number"/>
        <label>AsymptoteType:</label>
        <input v-model="asymptoteType" type = "text" readonly/>
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