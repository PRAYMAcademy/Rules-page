<template>
    <div class="pe-3 d-flex justify-content-center align-items-center">
        <a class="btn btn-primary align-items-center d-flex gap-2"
            href="https://docs.google.com/forms/d/e/1FAIpQLSd1-NvvZcdlqukBblog2wMygB-xj8p7VzM9QADWkeVWbMQeAQ/viewform?usp=header"
            target="_blank">
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