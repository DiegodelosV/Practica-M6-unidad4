<template>
  <button>
    <slot />
  </button>
</template>
<style scoped>
button {
  background: darkgreen;
  box-shadow: 4px 4px 20px 4px black;
  color: white;
  padding: 5px 20px;
  text-shadow: 1px 1px 1px black;
  border-radius: 15px;
}
</style>
