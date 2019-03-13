<template>
  <div id="app">
    <component :is="activeComponent" />
  </div>
</template>

<script>
import WhatVue from './components/WhatVue'
export default {
  name: 'app',
  components: {
    WhatVue
  },

  computed: {
    activeComponent () {
      return 'what-vue'
    }
  }
}
</script>

<style>
body {
  background-color: antiquewhite;
}
#app {
  height: 100vh;
  display: flex;
  justify-content: center;
  font-family: Arial;
  color: #246352;
  font-size: 20px;
  line-height: 2;
}
</style>
