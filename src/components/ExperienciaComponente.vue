<script setup>
</script>
<template>
    <div class="card">
        <h3 class="Titulo">Desarrollador Frontend</h3>
        <p class="fecha">Enero 2023-Diciembre 2024</p>
        <ul class=" listado">
            <li class="item"><img class="imagen svg" src="/src/assets/asterisco_icon.svg" width="45rem" alt="">
                <p>Contrucción de interfaz y estructura, traducción de diseño a código, conexión con el Backend, integración de APIs, conectando la interfaz de frontend con la lógica del negocio que recide en el Backend</p>
            </li>
             <li class="item"><img class="imagen svg" src="/src/assets/dos_icon.svg" width="45rem" alt="">
                <p>Estructuración de contenido utilzando HTML para definir estructuras y contenido semántico de la página</p>
            </li>
             <li class="item"><img class="imagen svg" src="/src/assets/tres_icon.svg"  width="45rem" alt="">
                <p>Aplicación de estilos, usando CSS y preprocesadores, como Less para darle estilo a la interfaz</p>
            </li>
             <li class="item"><img class="imagen svg" src="/src/assets/cuatro_icon.svg" width="45rem" alt="">
                <p>Desarrollo de funcionalidades con código fr Javascript para añadir interactividad al sitio, uso de frameworks y librerias</p>
            </li>
        </ul>


    </div>
</template>

<style scoped>
.card{
    display: flex;
    flex-direction: column;
    padding: 2rem;
    background-color: rgb(28, 41, 52);
    border-radius: 15px;
}
/* */
.titulo{
    font-size: 1.5rem;
    color: coral;
    
}
.fecha{
    font-size: 1rem;
    color: burlywood;
    margin-bottom: 1rem;
}
.listado{
    display: flex;
    flex-direction: column;
}
.item{
    align-items: center;
    display: flex;
    padding: 1rem;
    gap: 1.5rem;
}

</style>