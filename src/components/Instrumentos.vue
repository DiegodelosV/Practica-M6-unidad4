<script>
export default {
  props: ["foto", "nombre", "descripcion"],
}
</script>
<template>
  <div class="Instrumento">
    <div :style="{ backgroundImage: `url(${foto})` }" class="avatar"></div>
    <h2>{{ nombre }}</h2>
    <p>{{ descripcion }}-</p>
    <button @click="$emit('eliminarInstrumento')">Eliminar</button>
  </div>
</template>

<style scoped>
.Instrumento {
  margin-top: 10px;
  text-align: center;
  width: fit-content;
}
.avatar {
  background-image: url("https://cdn.pixabay.com/photo/2016/09/02/10/01/violin-1638742_1280.png ");
  background-size: cover;
  background-position: center;
  height: 200px;
  width: 200px;
  border-radius: 50%;
}
</style>
