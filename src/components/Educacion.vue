<script setup>
import { ref } from 'vue';
const fechaColor = ref([]);
fechaColor.value =[
    {color: '#11B5F8C'},
    {color: '#FBCA3E'},
    {color: '#E24A68'},
    {color: '#4CADAD'}
];
const educacion = ref ([]);
educacion.value = [
{fecha:'2025', titulo:'Tecnica Universitario en Programación', descripcion:'Conocimientos sobre lenguajes de programacion(Java, Javascript, Python), Lógica de programación y algoritmos, diseño y gestión de base de datos, desarrollo web (Front-end/Back-end) '},
{fecha:'2024', titulo:'Secretaria Administrativa', descripcion:'Gestion documental y de archivos, contabilidad y finanzas básicas, atención y comunicación, organización y planificación'},
{fecha:'2023', titulo:'Tecnica en Redes', descripcion:'Instalación y configuración de equipos, servicios básicos, mantenimiento y monitoreo, gestión de usuarios y accesos'},
{fecha:'2022', titulo:'Tecnica en Seguridad Informatica ', descripcion:'Prevención y protección de sistemas, redes y datos de una organización, monitoreo continuo, analisis de vulnerabilidades, '}
];
</script>

<template>
    <ul>
        <li v-for="(item, index) in educacion" :key="index" :style="{'--fecha-color': fechaColor[index].color}">
        <div class ="fecha">{{item.fecha}} </div>
        <h3 class ="title">{{item.title}}</h3>
        <div class = "descripcion">{{item.descripcion}}</div>
        <a class ="enlace" :href="item.enlace" target="_blank">Saber más</a>
    </li>
    </ul>    
</template>

<style scoped>
/*estilos generales */
@import url("https://fonts.googleapis.com/css2?family=Poppins:wwght@300;500;700&display=swap");
/*Reseteo de estilos basicos para todos los elmentos y pseudo-elementos */
*,
*::before
*::after{
    margin: 0;/*elimina el margin predeterminado */
    padding: 0;/*elimina el padding predeterminado */
    box-sizing: border-box;/*incluye el padding y el borde en el tamaño total del elemento */
}
/*Estilo para el cuerpo de la pagina */
body{
    --color: rgba(30,30,30);/*variable para el color del texto */
    --bgcolor: (245, 245, 245);/*variable para el color del fondo */
    min-height: 100vh;/*asegura que el cuerpo ocupe al menos el 100% de la altura de la ventana */
    display: grid;/*utiliza el modelo de caja de cuadricula */
    align-content: center;/*centra verticalmente el contenido dentro de la cuadricula */
    gap: 2rem;/*espaciado entre los elementos de la cuadricula */
    padding: 2rem;/*espaciado interno alrededor del cuerpo */
    font-family: "Poppins", sans-serif;/*fuente para todo el texto de la pagina */
    color: var(--color);/*aplica el color de texto definido en toda la variable */
    background: var(--color);/*aplica el color de fondo definido en la variable */
}
/*Estilo para la lista */
ul{
    margin-top: 2rem;
    --col-gap: 2rem;/*espacio ente las colimnas de la cuadricula */
    --row-gap: 2rem;/*espacio entre las filas de la cuadricula */
    --line-w:0.25rem;/*ancho de la línea que conecta los elementos de la lista */
    display: grid;/*usa un layout de cuadricula */
    grid-template-columns: var(--line-w)1fr;/*define las columnas de la cuadricula, la primera es la linea y la segunda es el contenido */
    grid-auto-columns: max-content;/*las columnas se ajustan automaticamente al contenido */
    column-gap: var(--col-gap);/*espacio entre columnas */
    list-style: none;/*elimina las viñetas predetermindas de la lista */
    width: min(60rem, 90%);/*limita el ancho de la lista al minimo entre 60 rem y el 90% del ancho de la ventana */
    margin-inline: auto;/*centra la lista horizontalmente */
}
/*Estilo para la linea vertical que conecta los elementos de la lista */
ul ::before{
    content: "";/*elemento vacio para crear la lista */
    grid-column: 1;/*coloca la linea en la primera columna de la lista */
    grid-row: 1 / span 20; /*la linea se extiende sobre varias filas */
    background: rgb(225, 225, 225);/*color de la linea */
    border-radius: calc(var(--line-w));/*bordes redondeados para la linea */
}
/*Estilo para los elementos de la lista que no son el ultimo */
ul :not(:last-child){
    margin-bottom: var(--row-gap);/*espacio entre los elementos de la lista */
}
/*Estilo para cada item de la lista */
ul li{
    grid-column: 2;/*coloca el contenido en la segunda columna de la cuadricula */
    --inlineP: 1.5rem;/*espacio interno horizontal dentro de cada item */
    margin-inline: var(--inlineP);/*margen horizontal para los items */
    grid-row: span 2;/*cada item opcupa dos filas de la cuadricula */
    display: grid;/**usa un lauyot de cuadricula dentro de cada item */
    grid-template-rows: min-content min-content min-content;/*define tres filas de altura minima */
}
/*Estilo para la fecha dentro de cada item */
ul li.fecha {
    --dateH: 3rem;/*altura de la seccion de la fecha */
    height: var(--dateH);/*aplica la altura definida */
    margin-inline: calc(var(--inlineP)) * -1;/*ajusta el margen horizontal para que la fecha sobresalga */
    text-align: center;/*centra el texto dentro de la fecha */
    background-color: var(--fecha-color);/*color de fondo usando una variable personalizada */
    color: white;/*color de texto en la fecha */
    font-size: 1.25rem;/*tamaño del texto */
    font-weight: 700;/*hace el texto en negrita */
    display: grid;/*usa yn loyuot de cuadricula */
    place-content: center;/*centra el contenido de la fecha */
    position: relative;/*posiciona la fecha relativa en su contenedor */
    border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2);/*bordes redondeados para la fecha */
}
/*estilos para la parte inferior de la fecha, que parece un triagulo */
ul li.fecha::before{
    content: "";/*elemento vacio para crear el triangulo */
    position: absolute;/*posiciona el circulo conrespecto al contendeor de la fecha */
    width: 1rem;/*ancho del circulo */
    aspect-ratio: 1;/*mantiene una relacion de aspecto 1:1 para crear un circilo */
    
}

</style>