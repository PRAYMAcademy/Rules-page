<template>
    <div class="bg-black bg-opacity-75 text-white rounded-4">
        <div class="p-2 justify-content-center align-items-center text-center mt-3">
            <div class="mapa-container">
                <h2 class="fw-bold text-decoration-underline">Ubicación del evento</h2>
                <div class="mapa-wrapper">
                    <iframe :src="mapaUrl" width="100%" height="300" style="border:0;" allowfullscreen="" loading="lazy"
                        referrerpolicy="no-referrer-when-downgrade">
                    </iframe>
                </div>
                <div class="pe-3 d-flex justify-content-center align-items-center">
                    <button @click="abrirRuta" class="btn btn-primary align-items-center d-flex gap-2 fs-5">
                        ¿Cómo llegar desde mi ubicación?
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            destino: "9.993272000401221,-84.66224275237705",
            mapaUrl: ""
        }
    },
    mounted() {
        // URL para mostrar el mapa embebido con la ubicación
        this.mapaUrl = `https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1000!2d-84.66224275237705!3d9.993272000401221!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zOcKwNTknMzUuOCJOIDg0wrAzOSc0NC4xIlc!5e0!3m2!1ses!2scr!4v1000000000000!5m2!1ses!2scr`;
    },
    methods: {
        abrirRuta() {
            navigator.geolocation.getCurrentPosition(position => {
                const lat = position.coords.latitude;
                const lng = position.coords.longitude;

                const url = `https://www.google.com/maps/dir/?api=1&origin=${lat},${lng}&destination=${this.destino}&travelmode=driving`;
                window.open(url, '_blank');
            }, error => {
                alert("No se pudo obtener tu ubicación.");
                console.error(error);
            });
        }
    }
}
</script>
