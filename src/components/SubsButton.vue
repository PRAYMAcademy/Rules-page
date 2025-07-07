<template>
    <div class="pe-3 d-flex justify-content-center align-items-center">
        <a class="btn btn-primary align-items-center d-flex gap-2" href="#">
            <img class="icon-form" :src="icon_form" alt="">
            Registrarse</a>
    </div>
</template>

<script setup>
defineProps({
    icon_form: {
        type: String,
        required: false
    }
})
</script>