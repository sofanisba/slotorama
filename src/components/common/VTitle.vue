<template lang="html">
  <h1 id="title">
    {{ text }}
  </h1>
</template>

<script>
export default {
  name: 'v-title',
  props: ['text']
}
</script>

<style lang="css" scoped>
#title {
  text-align: center;
  color: cadetblue;
}
</style>
