<template>
    <section>
        <Navbar logo="/src/assets/icons/logo.png" icon_form="src/assets/icons/archivo.png" />
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
            texto="Puedes elegir uno de los siguientes juegos como base para tu versión creativa:" :elements=datos />

        <Contenido titulo="Requisitos del juego" texto="" :lista="lista" />

        <div class="w-100 mt-3">
            <SubsButton icon_form="src/assets/icons/archivo.png" />
        </div>
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

const datos = [
    {
        id: 1, titulo: 'Pong', texto: 'Evitar que la bola se salga de la pantalla.', video: 'https://youtu.be/Yruv7QUiOJA?si=JO-CQ1PFRix6cOUo',
    },
    {
        id: 2, titulo: 'Saltar Plataformas', texto: 'Saltar por las plataformas.', video: 'https://youtu.be/QVfkpZGOGBY?si=IxWFWwkLT-263c0e',
    },
    {
        id: 3, titulo: 'Atrapa la Fruta', texto: 'Atrapa la fruta que aparece en la pantalla.', video: 'https://youtu.be/9XaRZ4WQ7d4?si=Iz7Yg2nZ4SfBcJtO',
    },
    {
        id: 4, titulo: 'Saltar y Esquivar', texto: 'Saltar y esquivar a los enemigos.', video: 'https://youtu.be/9XaRZ4WQ7d4?si=Iz7Yg2nZ4SfBcJtO',
    },
    {
        id: 5, titulo: 'Carrera de Autos', texto: 'Carrera de autos con obstáculos.', video: 'https://youtu.be/9XaRZ4WQ7d4?si=Iz7Yg2nZ4SfBcJtO',
    }
]

const lista = [
    { id: 1, texto: 'Debe estar hecho en Scratch 3.0.', },
    { id: 2, texto: 'Incluir una sola mecánica clara (ej: esquivar, atrapar, correr, saltar).', },
    { id: 3, texto: 'Tener 2 niveles de dificultad o dificultad progresiva.', },
    { id: 4, texto: 'Permitir que el estudiante modifique o cree sus propios diseños (personajes, fondos, obstáculos).', },
    { id: 5, texto: 'Diseños deben ser apropiados y no ofensivos.', },
]
</script>
