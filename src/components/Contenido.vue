<template>
    <div class="bg-black bg-opacity-50 text-white rounded-4 mb-2">
        <div class="p-2 justify-content-center align-items-center text-center mt-3">
            <div class="mb-3">
                <div class="">
                    <h1 class="fw-bold text-decoration-underline">{{ titulo }}</h1>
                </div>
                <div class="w-100 d-flex justify-content-center">
                    <div class="text-start text-content">
                        <p class="ps-3 pe-3">{{ texto }}</p>
                    </div>
                </div>
                <div v-if="elements && elements.length" class="d-flex flex-wrap gap-3 justify-content-center">
                    <Elementos v-for="element in elements" :key="element.id" :titulo="element.titulo"
                        :texto="element.texto" :video="element.video" :inicio=element.inicio :fin=element.fin :loop="false" />
                </div>
                <div v-if="lista && lista.length" class="w-100 d-flex justify-content-center">
                    <div class="text-start text-content">
                        <ol>
                            <li v-for="item in lista" :key="item.id">
                                {{ item.texto }}
                            </li>
                        </ol>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<script setup>
import Elementos from '@/components/Elementos.vue'

const props = defineProps({
    titulo: {
        type: String,
        required: true
    },
    texto: {
        type: String,
        required: false
    },
    elements: {
        type: Array,
        required: false
    },
    lista: {
        type: Array,
        required: false
    }
})

</script>