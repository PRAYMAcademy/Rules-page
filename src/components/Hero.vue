<template>
    <div class="text-center p-2 pb-4">
        <h1 class="text-decoration-underline">{{ titulo }}</h1>
        <hr class="text-white">
        <div class="pe-3 ps-3">
            <h3><span class="fw-bold">Tema:</span> Juegos Retro con Diseños Creativos</h3>
            <h3><span class="fw-bold">Fecha del evento:</span> Sá   bado 9 de agosto de 2025</h3>
            <h4 class="fw-bold">Inscripciones abiertas hasta el 18 de julio</h4>
        </div>
        <div class="pt-3">
            <SubsButton icon_form="" />
        </div>
    </div>
</template>

<script setup>
import SubsButton from './SubsButton.vue';
defineProps({
    titulo: {
        type: String,
        required: true
    }
})
</script>