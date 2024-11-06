<script>
function Coslaw() {
  cValue.value = Math.sqrt(a * a + b * b - (2 * a * b * Math.cos(C)));
}
</script>

<template>
<form action="/action_page.php">
        <h1>Cos law</h1>
        <label>a:</label>
        <input vue-model="side_a" type = "number"/>
        <label>b:</label>
        <input vue-model="text" type = "number"/>
        <label>C:</label>
        <input vue-model="text" type = "number"/>
        <label>c:</label>
        <input vue-model="text" type = "number" readonly/>
        <input type="button" value="Calculate"/>
 </form>

</template>

<style scoped>

</style>