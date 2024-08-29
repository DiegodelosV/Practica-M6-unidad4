<template>
  <section class="hero">
    <h1>Instrumentos Musicales</h1>
    <p>Bienvenido a mi sitio web. Explora y descubre cosas asombrosas.</p>
    <button>Empezar</button>
  </section>
</template>

<style scoped>
.hero {
  background-image: url("https://img.freepik.com/fotos-premium/diferentes-instrumentos-musicales-sobre-fondo-azul-banner-espacio-copia-logotipo-publicidad-texto-piano-guitarra-saxofon-tambores-concepto-escuela-musica-educacion-musical-representacion-3d_429124-3665.jpg?w=1380");
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 60vh;
  background-size: cover;
  background-position: center;
  object-fit: cover;
}
 .hero h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
  color: white;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.hero p {
  font-size: 1.2rem;
  margin-bottom: 30px;
  color: white;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

button {
  background-color: #ff6600;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 1rem;
  cursor: pointer;
}
</style>
