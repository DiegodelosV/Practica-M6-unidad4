<template>
  <div class="card">
    <div
      class="card-image"
      :style="{ backgroundImage: `url(${imagen})` }"
    ></div>
    <div class="card-content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ["imagen"],
};
</script>

<style scoped>
.card-image {
  background-size: cover;
  background-position: center;
  height: 180px;
  width: 200px;
}

.card {
  width: 200px;
  margin: 0 auto;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
</style>
