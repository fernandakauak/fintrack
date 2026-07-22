<script setup>
    import { ref } from 'vue';

    const categorias=ref([]);


    defineProps({
        categorias: { Type: Array, required: true },
        activa: { Type: String, required: true }
    });

    const emit= defineEmits('filtrar');
    const filtrar =()=> emit('filtrar');
// 🔨 [B · Req 8] Reciban 'categorias' (Array) y 'activa' (String) por props.
// 🔨 [B · Req 8] Declaren y emitan el evento 'filtrar' con la categoría elegida.
</script>

<template>
    <div class="filtro">
        <div class="chip" :class="{ activa: activa === nombre }">Todas</div>
        <div class="chip" v-for="categoria in categorias" :key="categoria.id" :class="{ activa: activa === nombre }">{{ categoria.nombre }}</div>
    </div>
    
  <!-- 🔨 [B] Un chip "Todas" + un chip por cada categoría (v-for).
       Marquen el activo con :class="{ activa: activa === nombre }"
       y al @click emitan 'filtrar' con ese nombre.
       Clases disponibles: .filtro, .chip, .chip.activa -->
</template>

<style scoped>
</style>