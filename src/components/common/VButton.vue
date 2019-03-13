<template lang="html">
  <button class="v-button">
    <slot />
  </button>
</template>

<style lang="css" scoped>
.v-button {
  background-color: coral;
  min-width: 300px;
  border: 1px solid orange;
  color: white;
  font-weight: bold;
  text-transform: uppercase;
  border-radius: 4px;
  padding: 15px;
}
.v-button:hover {
  background-color: brown;
  cursor: pointer;
}
</style>
