<template>
  <div>
    <Page :sidebar-items="sidebarItems"></Page>
    <SWUpdatePopup :updateEvent="swUpdateEvent"/>
  </div>
</template>

<script>
import Page from './Page.vue'
import SWUpdatePopup from './SWUpdatePopup.vue'

export default {
  components: { Page, SWUpdatePopup },

  data () {
    return {
      sidebarItems: [],
      swUpdateEvent: null
    }
  },

  mounted () {
    this.$on('sw-updated', this.onSWUpdated)
  },

  methods: {
    onSWUpdated (e) {
      this.swUpdateEvent = e
    }
  }
}
</script>

<style>

</style>
