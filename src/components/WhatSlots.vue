<template lang="html">
  <div id="what-slots">
    <v-title text="What are slots?" />

    <v-card>
      <span slot="header">This is slotted content</span>
      Vue implements a content distribution API inspired by the
      <a
        href="https://github.com/w3c/webcomponents/blob/gh-pages/proposals/Slots-Proposal.md"
        target="_blank"
      >
        Web Components
      </a>
      spec draft,using the slot element to serve as distribution outlets for
      content.

      <div slot="footer">
        <img src="http://www.sailorenergy.net/KawaiiGIFs/SMKSailorMoon.gif"/>
        <img src="http://www.sailorenergy.net/KawaiiGIFs/SMKSailorSuperMercury.gif" />
        <img src="http://www.sailorenergy.net/KawaiiGIFs/SMKSailorJupiter.gif" />
        <img src="http://www.sailorenergy.net/KawaiiGIFs/SMKSailorSuperVenus.gif"/>
        <img src="http://www.sailorenergy.net/KawaiiGIFs/SMKSailorSuperMars.gif" />
      </div>

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

img {
  margin-top: 5px;
}
</style>
