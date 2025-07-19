<template>
    <div class="bg-black bg-opacity-75 text-white rounded-4">
        <div class="p-2 justify-content-center align-items-center text-center mt-3">
            <div>
                <div class="">
                    <h1 class="fw-bold text-decoration-underline">{{ titulo }}</h1>
                </div>
                <div v-if="lista && lista.length" class="w-100 d-flex justify-content-center">
                    <div class="text-start text-content">
                        <p v-for="item in lista" :key="item.id"> {{ item.texto }} </p>
                    </div>
                </div>
                <div class="pt-1 pb-3">
                    <SubsButton :icon_form=icono />
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import SubsButton from './SubsButton.vue';

const props = defineProps({
    titulo: {
        type: String,
        required: true
    },
    lista: {
        type: Array,
        required: false
    },
    icono: {
        type: String,
        required: false
    }
})

</script>