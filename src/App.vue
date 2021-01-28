<template>
<b-container>
  <b-row>
    <b-col>
      <div id="app">
        <h1>PDF Homebase</h1>
        <div>
          <b-dropdown variant="success">
            <template #button-content>
              <!-- Custom <strong>Content</strong> with <em>HTML</em> via Slot -->
              <strong>Custom PDF</strong>-<em>Examples</em>
            </template>
            <b-dropdown-item href="#">Forms</b-dropdown-item>
            <b-dropdown-item href="#">HTML</b-dropdown-item>
            <b-dropdown-item href="#">CSS</b-dropdown-item>
          </b-dropdown>
        </div>
        <!-- <PdfTest /> -->
        
    <!-- <b-button variant='success' @click="makePdf">Make PDF</b-button> -->
    </div>
    </b-col>
  </b-row>
  </b-container>
</template>

<script>
// import PdfTest from "./components/PdfTEST.vue";
// import PdfHtmlTest from "./components/PdfHtmlTEST.vue";
// import jspdf from 'jspdf'

export default {
  name: "App",
  components: {
    // PdfTest, 
    // PdfHtmlTest,
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
