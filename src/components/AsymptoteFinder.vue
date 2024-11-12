<script setup>
import { ref } from 'vue';

const mValue = ref(0);
const nValue = ref(0);
const asymptoteType = ref(0);
function Asymptotecalculator() {
    let result;
    if (mValue.value === nValue.value) {
        result.value = "The asymptote is horizontal";
    } else if (nValue.value > mValue.value) {
        result = "The asymptote is the x-axis";
    } else {
        const Difference = mValue.value - nValue.value;
        switch (Difference) {
            case 1:
                result = "The asymptote is Linear";
                break;
            case 2:
                result = "The asymptote is Quadratic";
                break;
            case 3:
                result = "The asymptote is Cubic";
                break;
            case 4:
                result = "The asymptote is Quartic";
                break;
            case 5:
                result = "The asymptote is Quintic";
                break;
            case 6:
                result = "The asymptote is Sextic";
                break;
            case 7:
                result = "The asymptote is Septic";
                break;
            case 8:
                result = "The asymptote is Octic";
                break;
            case 9:
                result = "The asymptote is Nonic";
                break;
            case 10:
                result = "The asymptote is Decic";
        }
    }
    asymptoteType.value = result.value;
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
        <input v-model="asymptoteType" type = "number" readonly/>
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
    text-align: center;
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

input[type="number"] {
    width: 100%;
    padding: 10px;
    margin-bottom: 15px;
    font-size: 16px;
    border-radius: 8px;
    border: 1px solid #445;
    background-color: #333;
    color: #fff;
    box-sizing: border-box;
    transition: all 0.3s ease-in-out;
}

input[type="number"]:focus {
    border-color: #007bff;
    box-shadow: 0 0 8px rgba(76, 175, 80, 0.3);
    outline: none;
}

input[type="submit"] {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 12px 20px;
    border-radius: 5px;
    font-size: 16px;
    cursor: pointer;
    transition: all 0.3s ease-in-out;
}

input[type="submit"]:hover {
    background-color: #0056b3;
}

input[readonly] {
    background-color: #445;
    color: #aaa;
}

input[readonly]:focus {
    border-color: #445;
    box-shadow: none;
}
</style>