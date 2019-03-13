<template lang="html">
  <div id="whats-vue">
    <v-title text="What's Vue again?"/>

    <v-button @click.native="doSomething('with this')">
      Click Me
    </v-button>
    <br>
    <ul v-if="showMe">
      <li>Fun reactive framework!</li>
      <li>Declarative (look at my directives)</li>
      <li>"Approachable, Versatile and Performant" -- the Vue website</li>
    </ul>
  </div>
</template>

<script>
import VTitle from './common/VTitle'
import VButton from './common/VButton'
export default {
  name: 'whats-vue',
  components: {
    VTitle,
    VButton
  },

  data () {
    return {
      showMe: false
    }
  },

  methods: {
    doSomething (withWhat) {
      this.showMe = true
    }
  }
}
</script>

<style lang="css" scoped>
#whats-vue{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
