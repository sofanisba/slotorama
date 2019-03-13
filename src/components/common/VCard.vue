<template lang="html">
  <div class="v-card">
    <div class="header">
      <slot name="header" />
    </div>

    <div class="content">
      <!-- A <slot> outlet without name implicitly has the name “default”. -->
      <slot example="Whassap I'm a child"/>
    </div>

    <div class="footer">
      <slot name="footer" />
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="css" scoped>
.v-card {
  min-height: 400px;
  width: 300px;
  background-color: white;
  border: 1px solid lightgrey;
  border-radius: 2px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 5px 0;
}

.header {
  background-color: coral;
  text-align: center;
  color: white;
  min-height: 50px;
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
