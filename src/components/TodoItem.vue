<template>
  <ul class="todo-item">
    <li>
      {{ tarea }} <button @click="$emit('eliminarTarea')">Eliminar</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: ["tarea"],
};
</script>
