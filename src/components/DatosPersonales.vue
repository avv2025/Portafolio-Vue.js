<script setup>
const title= 'Andrea Vargas';
const descripcion= 'Técnica Universitaria en Programación-UTN';
const residencia= 'San Rafael-Mendoza';
const presentacion= 'Hola, Bienvenidos a mi portafolio de proyectos!Soy estudiante de Programación con conocimientos en los lenguajes de Python, Java y Javascript.';
const redesSociales= [
    {id: 1, name: 'Instagram', src: '/src/assets/instagram_icon.svg', url: ''},
    {id: 2, name: 'GitHub', src: '/src/assets/github_icon.svg', url: 'https://github.com/avv2025'},
    {id: 3, name: 'curriculum', src: '/src/assets/cv_resume_icon.svg', url: ''},
    {id: 4, name: 'linkedin', src: '/src/assets/linkedin_icon.svg', url: ''},
]
const telefono ="2604-823201"
</script>

<template>
<section class="datos-personales">
    <div class="card">
        <h1>{{ title }}</h1>
        <h2>{{ descripcion }}</h2>
        <p>{{ presentacion }}</p>
        <ul class="container-lista">
            <li v-for="red in redesSociales" :key="red.id">
                <a :href="red.url"><img class="icon-redsocial" :src="red.src" width="35" alt="red.name"></a>
            </li>
        </ul>
        <h3>Mi teléfono personal: {{ telefono }}</h3>
        <h4>{{ residencia }}</h4>
    </div>
</section>    

</template>

<style scoped>/*la palabra reservada: scoped significael estilo solo se aplica a esta plantilla */
h1 {

    font-size: 2.5rem;
}
p {
    font-size: 1.2rem;
    font-weight: 600;
    margin-bottom: 1rem;
}
.card {
    background-color: rgb(28, 41, 52);
    border-radius: 10px;
    padding: 10px;
    margin: 10px;
    text-align: center;
}
.container-lista{
    display: flex;
    justify-content: center;
    list-style: none;
    padding: 0;
    margin: 0;
    text-align: center;

}
.icon-redsocial {
    align-items: center;
    background-color: aliceblue;
    border-radius: 50%;
    padding: 2px;
    margin: 5px;
    box-shadow: 0 0 5px rgba(95, 124, 205, 0.934);
}
.icon-redsocial:hover {
    background-color: rgb(25, 41, 52);
    box-shadow: 0 0 5px rgba(95, 124, 205, 0.934);
}
h3 {
    font-size: 1.2rem;
    font-weight: 600;
}
</style>