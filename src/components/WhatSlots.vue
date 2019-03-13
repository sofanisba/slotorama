<template lang="html">
  <div id="what-slots">
    <v-title text="What are slots?" />

    <v-card>
      Vue implements a content distribution API inspired by the
      <a
        href="https://github.com/w3c/webcomponents/blob/gh-pages/proposals/Slots-Proposal.md"
        target="_blank"
      >
        Web Components
      </a>
      spec draft,using the slot element to serve as distribution outlets for
      content.
    </v-card>
  </div>
</template>

<script>
import VTitle from './common/VTitle'
import VCard from './common/VCard'
export default {
  name: 'what-slots',
  components: {
    VTitle,
    VCard
  }
}
</script>

<style lang="css" scoped>
#what-slots{

}
</style>
