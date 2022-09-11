<script setup>
import axios from 'axios';
import { ref } from 'vue';

const dolar = ref('');
const uf = ref('');
const fecha = ref('');
const loading = ref(true);

const getData = async () => {
  loading.value = true;
  try {
    const { data } = await axios.get('https://api-dolar-v26b.onrender.com/');
    // console.log(data);
    dolar.value = data.dolar;
    uf.value = data.UF;
    fecha.value = data.fecha;
  } catch (error) {
    console.log(error);
  } finally {
    loading.value = false;
  }
};
getData();
</script>

<template>
  <h1 v-if="loading">Loading data...</h1>
  <h1>Api Dolar Fecha: {{ fecha }} - Dolar: {{ dolar }} - UF: {{ uf }}</h1>
</template>
