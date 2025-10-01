<!--eslint-disable-next-line vue/multi-word-component-names-->
<script setup>

import { ref } from 'vue';
const fechaColor = ref([]);
fechaColor.value =[
    {color: '#41516c'},
    {color: '#FBCA3E'},
    {color: '#E24A68'},
    {color: '#1B5F8C'},
    {color: '#4CADAD'}
];
const educacion = ref ([]);
educacion.value = [
{fecha:'2025', title:'Tecnica Universitario en Programación', descripcion:'Conocimientos sobre lenguajes de programacion(Java, Javascript, Python), Lógica de programación y algoritmos, diseño y gestión de base de datos, desarrollo web (Front-end/Back-end)- '},
{fecha:'2024', title:'Secretaria Administrativa', descripcion:'Gestion documental y de archivos, contabilidad y finanzas básicas, atención y comunicación, organización y planificación-'},
{fecha:'2023', title:'Tecnica en Redes', descripcion:'Instalación y configuración de equipos, servicios básicos, mantenimiento y monitoreo, gestión de usuarios y accesos-'},
{fecha:'2022', title:'Tecnica en Seguridad Informatica ', descripcion:'Prevención y protección de sistemas, redes y datos de una organización, monitoreo continuo, analisis de vulnerabilidades-'},
{fecha:'2021', title:'Capacitacion de Desarrollo y Programacion ', descripcion:'Creación de software, aplicaciones y sitios web, lenguajes de programación, Python, Java, Base de datos para gestionar datos y sistemas como MySQL, Mongo DB, Cibercigerudad, hacking ético, analisis forense digital-'}
];
</script>

<template>
    <ul>
        <li v-for="(item, index) in educacion" :key="index" :style="{'--fecha-color': fechaColor[index].color}">
        <div class ="fecha">{{item.fecha}} </div>
        <h3 class ="title">{{item.title}}</h3>
        <div class ="descripcion">{{item.descripcion}}</div>
        <!--aqui vemos con el usi de b-vin (:) que bindeamos el atributo href del html con el item.enlace-->
        <a class ="enlace" :href="item.enlace" target="_blank">Saber más</a>
    </li>
    </ul>    
</template>

<style scoped>
/*estilos generales */
@import url("https://fonts.googleapis.com/css2?family=Poppins:wwght@300;500;700&display=swap");
/*Reseteo de estilos basicos para todos los elmentos y pseudo-elementos */
*,
*::before,
*::after {
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
ul {
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
ul ::before {
    content: "";/*elemento vacio para crear la lista */
    grid-column: 1;/*coloca la linea en la primera columna de la lista */
    grid-row: 1 / span 20; /*la linea se extiende sobre varias filas */
    background: rgb(225, 225, 225);/*color de la linea */
    border-radius: calc(var(--line-w));/*bordes redondeados para la linea */
}
/*Estilo para los elementos de la lista que no son el ultimo */
ul li:not(:last-child) {
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
ul li .fecha::before {
    content: "";/*elemento vacio para crear el triangulo */
    width: var(--inlineP);/*ancho igual al espacio interno definido */
    aspect-ratio: 1;/*mantiene una relacion de aspecto 1:1 para crear un circulo */
    background: var(--fecha-color);/*usa el color de fondo de la fecha */
    background-image: linear-gradient(rgba(0, 0, 0.2) 100%, transparent);/*aplica un degradado sutil para dar un efecto de sombra */
    position: absolute;/*posiciona el circulo conrespecto al contendeor de la fecha */
    top: 100%;/*coloca el triangulo justo debajo de la linea */
    clip-path: polygon(0 0 , 100% 0, 0 100%);/*recorta el cuadrado para converetilo en un triangulo */
    right: 0;/*alinea el triangulo a la derecha de la fecha */
}
/*Estilo para el circulo que conecta la fecha con la linea */
ul li .fecha::after{
    content: "";/*elemento vacio para crear el triangulo */
    position: absolute;/*posiciona el circulo conrespecto al contendeor de la fecha */
    width: 1rem;/*ancho del circulo*/
    aspect-ratio: 1;/*mantiene una relacion de aspecto 1:1 para crear un circulo */
    background: var(--bgcolor);/*color de fondo utilizando la variable definida */
    border: 0.3rem solid var(--fecha-color);/*borde del circulo con el color de la fecha */
    border-radius: 50%;/*hace que el elemento sea un circulo perfecto */
    top: 50%;/*centra verticalmente el circulo dentro del contenedor de la fecha*/
    transform: translate(50%, -50%);/*ajusta la posicion del circulo para alinearlo correctamente */
    right: calc(100% + var(--col-gap) + var(--line-w) / 2);/*coloca el circulo a la izquierda de la linea */
    
}
/*Estilo para el titulo y la descripcion de cada linea */
ul li .title, 
ul li .descripcion{
    background: var(--bgcolor);/*fondo del titulo y la descripcion usando la varibale definida */
    position: relative;/*posiciona los elementos relativos a su contenedor */
    padding-inline: 1.5rem;/*espaciado interno horizontal */
}
ul li .title{
    overflow: hidden;/*oculta cualquier contenido que se desborde */
    padding-block-start: 1.5rem;/*espaciado interno superior */
    padding-block-end: 1rem;/*espaciado interno inferior */
    font-weight: 500;/*hace el texto del titulo un poco mas grueso */
}
ul li .descripcion{
    padding-block-end: 1.5rem;/*espaciado interno inferior */
    font-weight: 300;/*hace el texto de la descripcion mas delgado */
}
/*Estilo de las ombras debajo del titulo y la descripcion */
ul li .title::before,
ul li .descripcion::before{
    content: "";/*elemento vacio para crear sombra */
    position: absolute;/*posiciona la sombra respecto al contenedor del titulo o la descripcion */
    width: 90%;/*ancho de la sombra */
    height: 0.5rem;/*altura de la sombra */
    background: rgba(0, 0, 0, 0.5);/*color de fondo ocsuro para simular una sombra */
    left: 50%;/*centra lasombra horizontalmente */
    border-radius: 50%;/*bordes redondeados para la sombra */
    filter: blur(4px);/*aplica un desenfoque para hacer las sombras mas suaves */
    transform: translate(-50%, 50%);/*ajusta la posicion para ajustar la sombra */
}
ul li .title::before{
    bottom: calc(100%, + 0.125rem);/*coloca la sombra debajo del titulo */
}
ul li .descripcion::before{
    z-index: -1;/*coloca la sombra detras del contenido */
    bottom: 0.25rem;/*coloca la sombra justo */
}
/*Media querys para pantallas anchas, 40rem o mas */
@media (min-width: 40rem){
    ul{
        grid-template-columns: 1fr var(--line-w);/*ajjusta la cuadricula para tener tres columnas */
    }
    ul ::before{
        grid-column: 2;/*mueve la linea vertical a la segunda columna de la cuadricula */
    }
    ul li:nth-child(odd){
        grid-column: 1;/*coloca los items impares en la primer columna */
    }
    ul li:nth-child(even){
        grid-column: 3;/*coloca los item pares para la tercer columna */
    }
    /*ajusta para que le segundo otem abarque dos columnas */
    ul li:nth-child(2){
        grid-row: 2/4;/*el segundo item ocupara desde la segunda hasta la cuarta linea */
    }
    /*Ajustes especificos para los items impares */
    ul li:nth-child(odd) .fecha::before {
        clip-path: polygon(0 0, 100% 0, 100% 100%);/*invierte el traingulo en los items impares */
        left: 0;/*alinea el triangulo a la izquierda */
    }
    ul li:nth-child(odd) .fecha::after{
        transform: translate(-50% 50%);/*ajusta la posicion del circulo a los items impares */
        left: calc(100% + var(--col-gap) + var(--line-w) / 2);/*coloca el circulo a la derecha de la linea */
    }
    ul li:nth-child(odd) .fecha{
        border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0;/*ajusta los bordes redondeados para los items impares */
    }
}
/*Estilo para los creditos */
.credits {
    margin-top: 1rem;/*espaciado superior para los creditos */
    text-align: right;/*alinea el texto de los creditos a la derecha */
}
.credits a{
    color: var(--color);/*aplica el color de texto definido */

}




</style>
