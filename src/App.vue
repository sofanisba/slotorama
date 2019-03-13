<template>
  <div id="app">
    <component :is="activeComponent" class="active"/>
  </div>
</template>

<script>
import WhatVue from './components/WhatVue'
import WhatSlots from './components/WhatSlots'
export default {
  name: 'app',
  components: {
    WhatVue,
    WhatSlots
  },

  computed: {
    activeComponent () {
      return 'what-slots'
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

.active {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
