<template>
    <div class="text-center p-2 pb-4">
        <h1 class="text-decoration-underline">{{ titulo }}</h1>
        <hr class="text-white">
        <div class="pe-3 ps-3">
            <h3><span class="fw-bold">Tema:</span> Juegos Retro con Diseños Creativos</h3>
            <h3><span class="fw-bold">Fecha del evento:</span> Sábado 9 de agosto de 2025</h3>
            <h4 class="fw-bold">Inscripciones abiertas hasta el 18 de julio</h4>
        </div>
        <div class="pt-3">
            <SubsButton
                link="https://docs.google.com/forms/d/e/1FAIpQLSd1-NvvZcdlqukBblog2wMygB-xj8p7VzM9QADWkeVWbMQeAQ/viewform?usp=header"
                texto="Registarse" :icon_form=icono />
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