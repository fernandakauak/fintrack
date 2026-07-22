<script setup>
// 🔨 [A · Req 1] Reciban 'categorias' por prop (para el <select>).
import {ref} from 'vue'

const emit = defineEmits(['agregar']);

const descripcion = ref('');
const monto = ref(0);
const categoria = ref('');  



//Enviar formulario 
const enviarFormulario = () => {
if(!descripcion.value || monto.value <=0 || !categoria.value) return;

  emit('agregar', {descripcion: descripcion.value, monto: monto.value, categoria: categoria.value});
  descripcion.value = '';
  monto.value = 0;
  categoria.value = '';  
}
</script>

<template>
  <form @submit.prevent="enviarFormulario">
    <input v-model="descripcion" placeholder="Descripción" type="text">
    <input v-model="monto" placeholder="Monto" type="number">
    <select v-model="categoria">
      <option v-for="categoria in categorias" :key="categoria" :value="categoria">
        {{ categoria }}
      </option>
    </select>
    <button type='submit'>Agregar</button>    
  </form>

</template>

<style scoped>
</style>