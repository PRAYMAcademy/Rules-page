<template>
    <div class="border rounded-3 p-3 box">

        <div class="d-flex justify-content-center align-items-center">
            <h2>{{ titulo }}</h2>
        </div>
        <div>
            <p>{{ texto }}</p>
        </div>
        <div class="">
            <iframe v-if="isYouTube" :src="embedUrl" title="YouTube video player" frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                allowfullscreen>
            </iframe>
        </div>
    </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
    titulo: {
        type: String,
        required: true
    },
    video: {
        type: String,
        default: ''
    },
    texto: {
        type: String,
        default: ''
    }
})


// Detectar si es un video de YouTube
const isYouTube = computed(() =>
    props.video.includes('youtube.com') || props.video.includes('youtu.be')
)

// Convertir la URL de YouTube a formato embed
const embedUrl = computed(() => {
    if (props.video.includes('watch?v=')) {
        return props.video.replace('watch?v=', 'embed/')
    } else if (props.video.includes('youtu.be')) {
        const id = props.video.split('youtu.be/')[1]
        return `https://www.youtube.com/embed/${id}`
    }
    return props.video
})
</script>

<style src="@/assets/main.css"></style>