<script>
import Header from "./components/Header.vue";
import Hero from "./components/Hero.vue";
import Instrumentos from "./components/Instrumentos.vue";
import TodoItem from "./components/TodoItem.vue";
import ButtonView from "./components/ButtonView.vue";
import CardView from "./components/CardView.vue";
import Letras from "./components/Letras.vue";
import Numeros from "./components/Numeros.vue";
import Home from "./components/Home.vue";
import Contacto from "./components/Contacto.vue";

export default {
  data() {
    return {
      instrumentos: [
        {
          foto: "https://cdn.pixabay.com/photo/2016/03/27/19/28/music-1283851_1280.jpg",
          nombre: "Violin",
          descripcion: "$700.000",
        },
        {
          foto: "https://cdn.pixabay.com/photo/2016/10/12/23/22/electric-guitar-1736291_1280.jpg",
          nombre: "Guitarra Electrica",
          descripcion: "$1.300.000",
        },
        {
          foto: "https://cdn.pixabay.com/photo/2018/09/26/01/06/piano-3703616_1280.jpg",
          nombre: "Piano",
          descripcion: "$2.500.000",
        },
      ],
      tareas: [
        "Aprender a tocar el piano",
        "Aprender a tocar el violín",
        "Aprender a tocar la guitarra eléctrica",
      ],
      componenteARenderizar: "",
      componentesNavbar: "Home", // Establecer Home como componente predeterminado
    };
  },
  components: {
    Header,
    Hero,
    Instrumentos,
    TodoItem,
    ButtonView,
    CardView,
    Letras,
    Numeros,
    Home,
    Contacto,
  },
  methods: {
    eliminarTarea(index) {
      this.tareas.splice(index, 1);
    },
  },
};
</script>

<template>
  <!-- Navbar dinámica -->
  <nav>
    <ul>
      <li>
        <a href="#" @click.prevent="componentesNavbar = 'Home'">Home</a>
      </li>
      <li>
        <a href="#" @click.prevent="componentesNavbar = 'Contacto'">Contacto</a>
      </li>
    </ul>
  </nav>

  <!-- Renderizar el componente seleccionado en la Navbar -->
  <component :is="componentesNavbar" />

  <!-- Header y Hero -->
  <div>
    <Header />
    <Hero />
  </div>

  <!-- Instrumentos con v-for -->
  <section class="musicales">
    <div v-for="(instrumento, i) in instrumentos" :key="i">
      <Instrumentos
        :foto="instrumento.foto"
        :nombre="instrumento.nombre"
        :descripcion="instrumento.descripcion"
        @eliminarInstrumento="instrumentos.splice(i, 1)"
      />
    </div>
  </section>

  <!-- Lista de tareas con v-for y eliminación de tareas -->
  <section class="tareas">
    <div v-for="(tarea, index) in tareas" :key="index">
      <TodoItem :tarea="tarea" @eliminarTarea="eliminarTarea(index)" />
    </div>
  </section>

  <!-- Uso de slot en ButtonView -->
  <div>
    <ButtonView>
      <h3>Este es el slot :o</h3>
    </ButtonView>
  </div>

  <!-- Card con slot -->
  <CardView
    imagen="https://cdn.pixabay.com/photo/2016/03/27/19/28/music-1283851_1280.jpg"
  >
    <h1>Violin</h1>
    <p>Este es un instrumento de cuerda y acústico</p>
    <button>Ver más</button>
  </CardView>

  <!-- Componentes de estado Letras y Numeros -->
  <div>
    <button @click="componenteARenderizar = 'Letras'">Letras</button>
    <button @click="componenteARenderizar = 'Numeros'">Números</button>
    <div>
      <component :is="componenteARenderizar" />
    </div>
  </div>
</template>

<style scoped>
.musicales {
  width: 80%;
  margin: 30px auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.tareas {
  margin-left: 30px;
}

nav {
  background: darkorange;
  color: white;
  padding: 5px;
  text-align: center;
}

nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

nav li {
  display: inline-block;
  margin: 0 10px;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-decoration: none;
}
</style>
