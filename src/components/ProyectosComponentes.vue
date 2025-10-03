<script setup>
</script>
<template>
    <div class="galeria">
        <div class="proyectos">
            <img src="/src/assets/annidada-tech.jpeg" alt="Proyecto 1">
            <div class="proyecto-info">
                <h3> Ecomerse</h3>
                <p>Creé una plataforma de comercio electrónico que incrementó las ventas en un 40% durante el primer año.</p>
                <div class="proyecto-links">
                    <a ref="https://github.com/usuario/proyecto1" class="github-link" target="_blank" rel="noopener noreferrer">Ver codigo en GitHub</a>
                </div>
            </div>        
        </div>

    </div>
</template>
<style scoped>

 .galeria{
    width: 100%;/*ancho */
    height: 100vh;/*alto */
    display: flex;
    flex-wrap: wrap ;/*se acomoda dentro del contenedor galeria */
    gap:20px;
    justify-content: center;/*las tarjetas quedan centradas dentro del proyectos */
    background-image: url('/src/assets/fondo.jpg');/*agregamos un imagen del componente */
    background-size: cover;/*la imagen ocupe todo el espacio */
    background-position: center;/*centrar imagen */
    background-repeat: no-repeat;/*la imagen no se repita*/
}

/*Estilol fondo animado de css en galeria */
.galeria{
    width: 100%;/*ancho */
    height: 100vh;/*alto */
    display: flex;
    flex-wrap: wrap ;/*se acomoda dentro del contenedor galeria */
    gap:20px;
    padding: 20px;
    justify-content: center;/*las tarjetas quedan centradas dentro del proyectos */
    background: linear-gradient(-45deg, #021526, #03346E, #6EACDA, #E2E2B6);
    background-size: 400% 400%;
    animation: gradient 15s ease infinite;
}
/*Define una animacion llamada gredient para cambiar la posicion del fondo */
@keyframes gradient {
    0%{
        background-position: 100% 50%;
    }
    100%{
        background-position: 0% 50%;
    }
}
.proyecto {
    display: flex;
    flex-direction: column;
    border: 2px #ddd;
    border-radius: 8px;
    overflow: hidden;
    background-color: #f9f9f9;
    max-width: 222px;
    flex:  1 1 300px;
}
.proyecto img {
    width: 100%;
    height: auto;
    display: block;
} 
.proyecto-info {
    padding: 15px;
    text-align: center;
}
.proyecto-info h3 {
    margin: 10px 0;
    font-size: 1.3rem;
    color: #333;
}
.proyecto-info p {
    margin: 10 px 0;
    font-size: 1rem;
    color: #666;
}
.proyecto-links {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 10px;
}
.proyecto-links .btn-ver.mas {
    background-color: #007BFF;
    color: #fff;
    padding: 10px 15px;
    border-radius: 5px;
    text-decoration: none;
    transition: background-color 0.3s;
}

.proyecto-links .btn-ver.mas:hover {
    background-color: #0056b3;
}
.proyecto-links .github-links {
    color: #333;
    text-decoration: none;
    font-size: 0.9rem;
}
/*Estilo para cuando el enlace a github es hover */
.proyecto-links .github-links:hover {
    text-decoration: underline;
}

</style>