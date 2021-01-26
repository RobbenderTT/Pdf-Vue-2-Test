<template>
  <div id="app">
    <PDFTEST />
  </div>
</template>

<script>
import PDFTEST from './components/PdfTEST.vue'

export default {
  name: 'App',
  components: {
    PDFTEST
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
