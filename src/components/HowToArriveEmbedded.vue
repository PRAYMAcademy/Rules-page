<template>
    <div class="mapa-container">
        <h3>Nuestra Ubicación</h3>
        <div class="mapa-wrapper">
            <iframe :src="embedUrl" width="100%" height="400" style="border:0;" allowfullscreen="" loading="lazy"
                referrerpolicy="no-referrer-when-downgrade">
            </iframe>
        </div>
        <div class="botones-container">
            <button @click="abrirRuta" class="btn btn-primary align-items-center d-flex gap-2">
                <i class="icon-navigation"></i>
                Cómo llegar desde mi ubicación
            </button>
            <button @click="copiarDireccion" class="btn-copiar">
                <i class="icon-copy"></i>
                Copiar coordenadas
            </button>
        </div>
        <div v-if="mostrarMensaje" class="mensaje-copiado">
            ¡Coordenadas copiadas al portapapeles!
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            destino: "9.993272000401221,-84.66224275237705",
            embedUrl: "",
            mostrarMensaje: false
        }
    },
    mounted() {
        // Para una implementación más robusta, deberías obtener una API key de Google Maps
        // y usar la Google Maps Embed API oficial
        this.embedUrl = `https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d15720.123456789!2d-84.66224275237705!3d9.993272000401221!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zOcKwNTknMzUuOCJOIDg0wrAzOSc0NC4xIlc!5e0!3m2!1ses!2scr!4v${Date.now()}!5m2!1ses!2scr`;
    },
    methods: {
        abrirRuta() {
            navigator.geolocation.getCurrentPosition(position => {
                const lat = position.coords.latitude;
                const lng = position.coords.longitude;

                const url = `https://www.google.com/maps/dir/?api=1&origin=${lat},${lng}&destination=${this.destino}&travelmode=driving`;
                window.open(url, '_blank');
            }, error => {
                alert("No se pudo obtener tu ubicación. Por favor, habilita la geolocalización en tu navegador.");
                console.error(error);

                // Fallback: abrir solo la ubicación de destino
                const fallbackUrl = `https://www.google.com/maps/place/${this.destino}`;
                window.open(fallbackUrl, '_blank');
            });
        },

        async copiarDireccion() {
            try {
                await navigator.clipboard.writeText(this.destino);
                this.mostrarMensaje = true;
                setTimeout(() => {
                    this.mostrarMensaje = false;
                }, 3000);
            } catch (err) {
                console.error('Error al copiar al portapapeles:', err);
                // Fallback para navegadores que no soportan clipboard API
                this.fallbackCopiarTexto(this.destino);
            }
        },

        fallbackCopiarTexto(texto) {
            const textArea = document.createElement('textarea');
            textArea.value = texto;
            document.body.appendChild(textArea);
            textArea.focus();
            textArea.select();
            try {
                document.execCommand('copy');
                this.mostrarMensaje = true;
                setTimeout(() => {
                    this.mostrarMensaje = false;
                }, 3000);
            } catch (err) {
                console.error('Fallback: No se pudo copiar el texto');
            }
            document.body.removeChild(textArea);
        }
    }
}
</script>

<style scoped>
.mapa-container {
    padding: 20px;
    text-align: center;
    max-width: 800px;
    margin: 0 auto;
}

.mapa-container h3 {
    margin-bottom: 20px;
    color: #333;
    font-size: 24px;
    font-weight: 600;
}

.mapa-wrapper {
    margin-bottom: 20px;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
    background: #f5f5f5;
}

.botones-container {
    display: flex;
    gap: 15px;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 15px;
}

.btn-ruta,
.btn-copiar {
    background: linear-gradient(135deg, #4285f4, #34a853);
    color: white;
    border: none;
    padding: 12px 24px;
    border-radius: 25px;
    cursor: pointer;
    font-size: 16px;
    font-weight: 500;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    gap: 8px;
    box-shadow: 0 4px 12px rgba(66, 133, 244, 0.3);
}

.btn-copiar {
    background: linear-gradient(135deg, #6c757d, #495057);
    box-shadow: 0 4px 12px rgba(108, 117, 125, 0.3);
}

.btn-ruta:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 16px rgba(66, 133, 244, 0.4);
}

.btn-copiar:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 16px rgba(108, 117, 125, 0.4);
}

.mensaje-copiado {
    background-color: #4caf50;
    color: white;
    padding: 10px 20px;
    border-radius: 20px;
    display: inline-block;
    animation: fadeInOut 3s ease-in-out;
    font-weight: 500;
}

@keyframes fadeInOut {
    0% {
        opacity: 0;
        transform: translateY(10px);
    }

    20% {
        opacity: 1;
        transform: translateY(0);
    }

    80% {
        opacity: 1;
        transform: translateY(0);
    }

    100% {
        opacity: 0;
        transform: translateY(-10px);
    }
}

/* Iconos simples usando CSS */
.icon-navigation::before {
    content: "🧭";
    margin-right: 5px;
}

.icon-copy::before {
    content: "📋";
    margin-right: 5px;
}

/* Responsive */
@media (max-width: 768px) {
    .mapa-container {
        padding: 15px;
    }

    .botones-container {
        flex-direction: column;
        align-items: center;
    }

    .btn-ruta,
    .btn-copiar {
        width: 100%;
        max-width: 300px;
    }
}
</style>
