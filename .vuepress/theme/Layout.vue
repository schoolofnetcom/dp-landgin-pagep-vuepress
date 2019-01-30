<template>
  <div>
    <header id="header">
      <h1>Laravel 5.7 <small>e-book para iniciantes</small></h1>
      <img src="../../assets/icon-computer.png">
    </header>
    <Page :sidebar-items="sidebarItems"></Page>
    <SWUpdatePopup :updateEvent="swUpdateEvent"/>
    <footer id="footer">
      Todos os direitos reservados
    </footer>
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
  @import url('https://fonts.googleapis.com/css?family=Lato:400,400i,700');

  * {
    box-sizing: border-box;
  }
  
  html, body, #app, #app > div {
    height: 100%;
  }

  body {
    font-family: 'Lato', sans-serif;
    font-size: 16px;
    margin: 0;
    padding: 0;
    background: url(../../assets/laravel-logo-gray.png) no-repeat;
  }

  #app > div {
    display: flex;
    flex-direction: column;
  }

  #header {
    flex: 0 0 400px;
    background: #f26c4f url(../../assets/laravel-logo.png) no-repeat;
    color: white;
    padding: 20px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  #header h1 {
    align-self: center;
    font-size: 72px;
  }

  #header h1 small {
    display: block;
    font-size: 30px;
  }

  #header img {
    margin: 20px;
    width: 360px;
    height: 360px;
  }

  .page {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    flex: 1;
    padding: 20px;
  }

  .content {
    display: flex;
    flex-direction: row;
    align-items: center;
    height: 100%;
  }

  .content img {
    height: 200px;
  }

  .content > div, .content > form {
    flex: 1;
    padding: 0 20px;
  }

  .content > p:first-child {
    width: 145px;
  }

  #footer {
    text-align: center;
    padding: 5px;
    background: #e1e1e1;
  }
</style>

