<script setup>
import { ref, computed } from 'vue'
import FormularioGasto from './components/FormularioGasto.vue';
// 🔨 Importen aquí sus 4 componentes cuando los tengan.

// ===== CONTRATO: categorías válidas (dato acordado, NO lo inventen) =====
const categorias = [
  { nombre: 'Comida',     emoji: '🍔' },
  { nombre: 'Transporte', emoji: '🚗' },
  { nombre: 'Súper',      emoji: '🛒' },
  { nombre: 'Ocio',       emoji: '🎬' },
  { nombre: 'Otros',      emoji: '📦' },
]

// El estado vive en el padre. Forma de cada gasto: { id, descripcion, monto, categoria }
const gastos = ref([])

// 🔨 CONSTRUYAN todo esto (revisen el contrato y los requisitos):
//    · estado del filtro
//    · métodos: agregarGasto, eliminarGasto, ajustarMonto, cambiarFiltro
//    · computed: total, porCategoria, gastosVisibles
</script>

<template>
  <h1>💸 FinTrack</h1>
  <div class="finapp">
    <FormularioGasto @agregar="agregarGasto" :categorias="categorias" />
    
    <!-- 🔨 Izquierda (.card): FormularioGasto + FiltroCategoria + lista de ItemGasto (v-for) -->
    <!-- 🔨 Derecha (.card): PanelResumen -->
    <!-- Conecten props (:) y eventos (@) según el contrato. -->
  </div>
</template>