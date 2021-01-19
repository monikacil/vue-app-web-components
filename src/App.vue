<template>
  <div id="app">
    <button @click="openModal()">Open modal</button>
    <custom-modal title="Modal Web Components" 
                  button="Save"
                  :open="modalIsOpen"
                  @close="closeModal()" 
                  @btn-click="sendData()">
      <div slot="content">
        <p>{{ message }}</p>
      </div>
    </custom-modal>
  </div>
</template>

<script>

import 'custom-modal-web-component/dist/bundle.min.js'

export default {
  name: 'App',
  data() {
    return {
      modalIsOpen: false,
      message: 'Przykładowy komponent okna dialogowego w aplikacji Vue.'
    }
  },

  methods: {
    openModal: function() {
      this.modalIsOpen = true
    },
    closeModal: function() {
      this.modalIsOpen = false
     
    },
    sendData: function() {
      console.log('Event form Save button')
    }
  }
}
</script>

<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
}
</style>
