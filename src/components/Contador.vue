<template>
    <h1>Hola Mundo</h1>
    <p>{{ contador }}</p>
    <button @click="restar">Restar</button>
    <button @click="incrementar">Incrementar</button>
</template>

<script setup>
import { ref } from 'vue';
const contador = ref(0);
const incrementar = () => {
    contador.value+=1;
}
const restar = () => {
    contador.value--;
}
</script>

<style scoped>
p {
    color: red;
}
</style>