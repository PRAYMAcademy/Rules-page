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
    titulo: { type: String, required: true },
    video: { type: String, default: '' },
    texto: { type: String, default: '' },
    inicio: { type: Number, default: 0 },     // en segundos
    fin: { type: Number, default: 0 },        // en segundos (si 0, no se pone)
    loop: { type: Boolean, default: true }
})

const isYouTube = computed(() =>
    props.video.includes('youtube.com') || props.video.includes('youtu.be')
)

const embedUrl = computed(() => {
    let videoId = ''

    if (props.video.includes('watch?v=')) {
        videoId = props.video.split('watch?v=')[1].split('&')[0]
    } else if (props.video.includes('youtu.be')) {
        videoId = props.video.split('youtu.be/')[1].split('?')[0]
    }

    const base = `https://www.youtube.com/embed/${videoId}`
    const startParam = `start=${props.inicio}`
    const endParam = props.fin ? `&end=${props.fin}` : ''
    const autoplay = 'autoplay=0'
    const loopParam = props.loop ? `&loop=1&playlist=${videoId}` : ''
    const mute = '&mute=1' // opcional: evita que el autoplay sea bloqueado

    return `${base}?${autoplay}&${startParam}${endParam}${loopParam}${mute}`
})
</script>

<style src="@/assets/main.css"></style>