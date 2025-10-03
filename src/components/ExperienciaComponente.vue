<script setup>
import { ref } from 'vue';
const titulo='Desarrollador Frontend';
const fecha='Enero 2023-Diciembre 2024';
const experiencias=ref([
    {id:1, src:'/src/assets/asterisco_icon.svg', parrafo:'Junto a un equipo de trabajo realizamos la contrucción de interfaz y estructura, traducción de diseño a código, conexión con el Backend, integración de APIs'},
    {id:2, src:'/src/assets/dos_icon.svg', parrafo:'Realicé estructuración de contenido utilzando HTML para definir estructuras y contenido semántico de la página'},
    {id:3, src:'/src/assets/tres_icon.svg', parrafo:'Realicé aplicación de estilos, usando CSS y preprocesadores, como Less para darle estilo a la interfaz'},
    {id:4, src:'/src/assets/cuatro_icon.svg', parrafo:'Implementé el desarrollo de funcionalidades con código fr Javascript para añadir interactividad al sitio, uso de frameworks y librerias'},
    ])
</script>
<template>
    <div class="card">
        <h3 class="Titulo">{{ titulo.toLocaleUpperCase() }}</h3>
        <p class="fecha">{{ fecha }}</p>
        <ul class=" listado">
            <li class="item" v-for="experiencia in experiencias" :key="experiencia.id">
                <img class="imagen-svg" :src="experiencia.src" width="45rem" :alt="experiencia.parrafo">
                <p>{{ experiencia.parrafo }}</p>

            </li>

            <!--li class="item"><img class="imagen svg" src="/src/assets/asterisco_icon.svg" width="45rem" alt="">
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
            </li-->
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