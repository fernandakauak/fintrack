<script setup>
    const props= defineProps({
        gasto: { type: Object, required: true}
    });

    const emit= defineEmits(['eliminar','ajustar', 'agregar']);

    const eliminar =()=> emit('eliminar', props.gasto.id);
    const ajustar =()=> emit('ajustar', props.gasto.id, -500);
    const agregar =()=> emit('agregar', props.gasto.id, 500);

    // 🔨 [B · Req 3] Reciban el gasto por prop, con validación (type Object, required).
    // 🔨 [B · Req 5] Declaren los eventos 'eliminar' y 'ajustar' (defineEmits).


    //               El hijo NO borra ni cambia el monto: SOLO emite (con el id).

    // Mapa de emojis por categoría (dato acordado, úsenlo):
    const emojis = { Comida:'🍔', Transporte:'🚗', Super: '🛒', Ocio:'🎬', Otros:'📦' }
</script>

<template>
    <p class="gasto-item"><span class="emoji">{{ emojis.Comida }}</span> Comida <strong>$ </strong><button class="mini">+</button><button class="mini">-</button><button class="mini del">x</button></p>
    <p class="gasto-item"><span class="emoji">{{ emojis.Transporte }}</span> Transporte <strong>$00</strong><button class="mini">+</button><button class="mini">-</button><button class="mini del">x</button></p>
    <p class="gasto-item"><span class="emoji">{{ emojis.Super }}</span> Super <strong>$00</strong><button class="mini">+</button><button class="mini">-</button><button class="mini del">x</button></p>
    <p class="gasto-item"><span class="emoji">{{ emojis.Ocio }}</span> Ocio <strong>$00</strong><button class="mini">+</button><button class="mini">-</button><button class="mini del">x</button></p>
    <p class="gasto-item"><span class="emoji">{{ emojis.Otros }}</span> Otros <strong>$00</strong><button class="mini">+</button><button class="mini">-</button><button class="mini del" @click="eliminar">x</button></p>

    <!-- 🔨 [B] Una fila con: emoji de la categoría (emojis[gasto.categoria]),
        descripción, monto formateado, y botones  −  +  ✕  que emitan
        ajustar(id,-500) / ajustar(id,500) / eliminar(id).
        Clases disponibles: .gasto-item, .emoji, .desc, .monto, .mini, .mini.del -->
</template>

<style scoped>
</style>