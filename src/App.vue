<template>
    <section>
        <Navbar :logo=logo_route :icono="icon_form_route" />
    </section>
    <section class="container pt-4">
        <div class="bg-black bg-opacity-50 text-white rounded-4">
            <Hero titulo="RETO DE VIDEOJUEGOS EN SCRATCH 3.0" />
        </div>
    </section>
    <section class="container pt-2">

        <Contenido titulo="Objetivo del reto"
            texto="Desarrollar un videojuego en Scratch 3.0 con una mecánica clara e inspiración en juegos retro, promoviendo la creatividad, la lógica de programación y el diseño personal." />

        <Contenido titulo="Temática: Juegos Retro"
            texto="A continuación te compartimos algunos ejemplos de juegos retro que pueden ser tomados en cuenta para tu idea:"
            :elements=datos />

        <Contenido titulo="Requisitos del juego" texto="" :lista="lista" />

        <Multilinea titulo="¡Manos a la obra!" :lista="informacion" :icono="icon_form_route" />
    </section>
    <section class="pt-4">
        <Footer />
    </section>

</template>

<script setup>
import Contenido from '@/components/Contenido.vue'
import Navbar from '@/components/Navbar.vue'
import Footer from '@/components/Footer.vue'
import Hero from '@/components/Hero.vue'
import SubsButton from '@/components/SubsButton.vue'
import Multilinea from './components/Multilinea.vue'

import icon_form_route from '@/assets/icons/archivo.png'
import logo_route from '@/assets/icons/PRAYM-logo.png'

const datos = [
    {
        id: 1, titulo: 'Pong', texto: 'Evitar que la bola se salga de la pantalla.', video: 'https://youtu.be/Yruv7QUiOJA?si=JO-CQ1PFRix6cOUo', inicio: 0, fin: 20
    },
    {
        id: 2, titulo: 'Saltar Plataformas', texto: 'Saltar por las plataformas.', video: 'https://youtu.be/QVfkpZGOGBY?si=IxWFWwkLT-263c0e', inicio: 10, fin: 30
    },
    {
        id: 3, titulo: 'Atrapa la Fruta', texto: 'Atrapa la fruta que aparece en la pantalla.', video: 'https://youtu.be/31Cj7R6KQa0?si=6idrnyftNXtSmYAA', inicio: 0, fin: 21
    },
    {
        id: 4, titulo: 'Saltar y Esquivar', texto: 'Saltar y esquivar a los enemigos.', video: 'https://www.youtube.com/watch?v=KJkcNP4VkiM&list=RDKJkcNP4VkiM&start_radio=1', inicio: 21, fin: 40
    },
    {
        id: 5, titulo: 'Carrera de Autos', texto: 'Carrera de autos con obstáculos.', video: 'https://youtu.be/1YrIuey9Vms?si=ngytJDWxwPh9zSgn', inicio: 11, fin: 22
    }
]

const lista = [
    { id: 1, texto: 'El juego de estar desarrollado en Scratch 3.0.', },
    { id: 2, texto: 'Como minimo se debe poder identificar una mecanica clara. (ej: esquivar, atrapar, correr, saltar, etc). ', },
    { id: 3, texto: 'Como minimo, debe tener 2 niveles de dificultad o dificultad progresiva (aumenta la dificultad cada vez que el juego avanza)', },
    { id: 4, texto: 'El estudiante debe crear o modificar los diseños de sus propios personajes, fondos y escenarios.', },
    { id: 5, texto: 'Los diseños deben ser adecuados para todo público y no contener contenido ofensivo, violento o discriminatorio.', },
]

const informacion = [
    { id: 1, texto: 'Tienes hasta finales de julio para crear tu juego.', },
    { id: 2, texto: 'Recuerda: lo más importante es divertirse, aprender y crear algo propio.', },
    { id: 3, texto: '¡Te esperamos en el reto Scratch Retro PRAYM!', },
]
</script>
