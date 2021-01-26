<template>
<b-container>
  <b-row>
    <b-col>
      <div id="app">
        <PdfTest />
    <!-- <b-button variant='success' @click="makePdf">Make PDF</b-button> -->
    </div>
    </b-col>
  </b-row>
  </b-container>
</template>

<script>
import PdfTest from "./components/PdfTEST.vue";
// import jspdf from 'jspdf'

export default {
  name: "App",
  components: {
    PdfTest,
  },
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* background-color: black; */
  padding: 50px;
}
</style>
