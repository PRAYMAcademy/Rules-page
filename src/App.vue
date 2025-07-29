<template>
    <section>
        <Navbar :logo=logo_route :icono="icon_form_route" />
    </section>
    <section class="container pt-4">
        <div class="bg-black bg-opacity-75 text-white rounded-4">
            <Hero titulo="RETO DE VIDEOJUEGOS EN SCRATCH 3.0" />
        </div>
    </section>
    <section class="container pt-2">

        <Contenido titulo="Objetivo del reto"
            texto="Desarrollar un videojuego en Scratch 3.0 con una mecánica clara e inspiración en juegos retro, promoviendo la creatividad, la lógica de programación y el diseño personal." />

        <Contenido titulo="Temática: Juegos Retro"
            texto="A continuación te compartimos algunos ejemplos de juegos retro que pueden ser tomados en cuenta para tu idea:"
            :elements=datos />

        <Contenido titulo="Requisitos del juego" texto="" :lista="reglas" />

        <Contenido titulo="Cronograma de la actividad" texto="">
            <img src="..\src\assets\icons\cronograma.jpg" alt="" srcset="">
        </Contenido>

        <Contenido titulo="Rubrica de evaluación"
            texto="Esta es la rubrica de evaluación que se usará para calificar a los participantes durante el reto.">
            <SubsButton link="src\assets\test.pdf" texto="Rubrica" :icon_form=icon_form_route />
        </Contenido>

        <Contenido titulo="Datos de importancia" texto="" :lista="importancia" />

        <HowToArrive />

        <Contenido titulo="Dudas y consultas"
            texto="Si tienes alguna duda o consulta, no dudes en contactarnos al 88176498 - Moisés Mendez." />

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
import Multilinea from './components/Multilinea.vue'
import HowToArrive from './components/HowToArrive.vue'
import SubsButton from '@/components/SubsButton.vue';

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

const reglas = [
    { id: 1, texto: 'El juego debe estar desarrollado en Scratch 3.0.', },
    { id: 2, texto: 'Como mínimo se debe poder identificar una mecánica clara. (ej: esquivar, atrapar, correr, saltar, etc).', },
    { id: 3, texto: 'El proyecto debe tener un título creativo y una descripción breve que explique su objetivo.', },
    { id: 4, texto: 'Como mínimo, debe tener 2 niveles de dificultad o dificultad progresiva (aumenta la dificultad cada vez que el juego avanza).', },
    { id: 5, texto: 'El estudiante debe crear o modificar los diseños de sus propios personajes, fondos y escenarios.', },
    { id: 6, texto: 'Los diseños deben ser adecuados para todo público y no contener contenido ofensivo, violento o discriminatorio.', },
    { id: 7, texto: 'El juego debe incluir sonidos o música de fondo para crear una experiencia más inmersiva.', },
    { id: 8, texto: 'Debe tener un sistema de puntuación visible que permita al jugador cotrolar el avance.', },
    { id: 9, texto: 'El juego debe tener una ejecución claro e intuitivo para los jugadores.', },
    { id: 10, texto: 'El juego debe estar optimizado para jugarse en pantalla completa y no debe tener errores visibles al ejecutar', },
    { id: 11, texto: 'Debe incluir una pantalla de "You Win / Tenemos Ganador" personalizada al conseguir la puntuación máxima.', },
    { id: 12, texto: 'Debe incluir una pantalla de "Game Over / Perdiste" personalizada cuando el jugador pierda.', },
    { id: 13, texto: 'Los videojuegos deben ser entregados antes de la fecha establecida (2 de agosto de 2025).', },
    { id: 14, texto: 'El videojuego debe estar publicado en la carpeta de drive asignada a cada participante.', },
    { id: 15, texto: 'El juego debe permitir al jugador interactuar durante al menos 60 segundos.', },
    { id: 16, texto: 'El participante debebrá desarrollar una presentación oral de un maximo de 10 minutos en la cual expondrá el desarollo y uso del videojuego.', },
    { id: 17, texto: 'Respeto y juego limpio: Se espera un comportamiento respetuoso entre todos los participantes durante la totalidad del evento.', },
    { id: 18, texto: 'Resolución de conflictos: Cualquier controversia será resuelta por el jurado o comité organizador, y su decisión será definitiva.', },
    { id: 19, texto: 'El plagio de código o ideas será motivo de descalificación inmediata.', },
]

const informacion = [
    { id: 1, texto: 'Tienes hasta el 2 de agosto del 2025 para crear tu juego.', },
    { id: 2, texto: 'Recuerda: lo más importante es divertirse, aprender y crear algo propio.', },
    { id: 3, texto: '¡Te esperamos en el reto Scratch Retro PRAYM!', },
]

const importancia = [
    { id: 1, texto: 'Parqueo limitado.', },
    { id: 2, texto: 'Los participantes contarán con alimetación.', },
    { id: 3, texto: 'Se les recuerda a los padre de familia que es un evento recreativo con el fin de fomentar la sana competencia y contribuir en la mejora de habilidades blandas.', },
    { id: 4, texto: 'Se les recuerda a los padre de familia, conversar con sus hijos que un puesto no nos define, solo nos da las alas para aprender y mejorar continuamente.', },
    { id: 5, texto: 'Se les insta a apoyar el proceso educativo de sus hijos al incluir a familiares y amigos al evento.', },
    { id: 6, texto: 'Importante: Al ser un evento familiar y educativo, la vestimenta debe ser acorde a la actividad.', },
]
</script>
