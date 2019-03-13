<template lang="html">
  <div class="v-card">
    <div class="header">
      A Header
    </div>

    <div class="content">
      <slot />
    </div>

    <div class="footer">
      A Footer
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="css" scoped>
.v-card {
  height: 400px;
  width: 300px;
  background-color: white;
  border: 1px solid lightgrey;
  border-radius: 2px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.header {
  background-color: coral;
  text-align: center;
  color: white;
}

.content {
  padding: 10px;
  font-size: 18px;
  line-height: 1.5;
}

.footer {
  display: flex;
  justify-content: center;
  border-top: 1px solid lightgrey;
  color: grey;
}
</style>
