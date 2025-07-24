<template>
    <div class="pe-3 d-flex justify-content-center align-items-center">
        <a class="btn btn-primary align-items-center d-flex gap-2 fs-4" :href="link" target="_blank">
            <img class="icon-form" :src="icon_form" alt="">
            {{ texto }}</a>
    </div>
</template>

<script setup>
defineProps({
    icon_form: {
        type: String,
        required: false
    },
    texto: {
        type: String,
        required: true
    },
    link: {
        type: String,
        required: true
    }
})
</script>