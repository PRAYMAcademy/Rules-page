<template>
    <nav class="navbar justify-space-between bg-dark bg-opacity-75">
        <div class="ps-3 d-flex justify-content-center align-items-center">
            <div class="">
                <img class="icon" :src="logo" alt="logo">
            </div>
        </div>
        <SubsButton icon_form="src/assets/icons/archivo.png"/>
    </nav>
</template>

<script setup>
import SubsButton from './SubsButton.vue';
defineProps({
    logo: {
        type: String,
        required: true
    }
})
</script>
