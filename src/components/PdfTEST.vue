<template>
<b-container>
  <div class="">
    <h2 ref="content">Client PDF</h2>
  <b-row>
    <b-col>
      <b-alert 
          :show="dismissCountDown"
          dismissible
          variant="info"
          @dismissed="dismissCountDown=0"
          @dismiss-count-down="countDownChanged"
          >Generating your PDF, please wait...</b-alert>
      <div id="app">
        <!-- <h5>Please fill out all fields</h5> -->
        <b-button variant='success' @click="makePdf">Make PDF</b-button>
      </div>
      <div>
        <b-form-group id="fieldset-name">
						<b-form-input id="name" v-model="name" placeholder="Name"></b-form-input>
				</b-form-group>
      </div>
      <div>
        <b-form-group id="fieldset-name">
						<b-form-input id="address" v-model="address" placeholder="Address"></b-form-input>
				</b-form-group>
      </div>
      <div>
      <b-form-textarea
                id="textarea"
                v-model="description"
                placeholder="Description"
                rows="5"
                max-rows="10"
              ></b-form-textarea>
               <!-- <pre class="mt-3 mb-0">{{ influencer_description }}</pre> -->
      </div>
      <br>
      <br>
      <div class="text-left">
          <b-form-group label="Individual radios" v-slot="{ ariaDescribedby }">
            <b-form-radio v-model="selected" :aria-describedby="ariaDescribedby" name="some-radios" value="A">Option A</b-form-radio>
            <b-form-radio v-model="selected" :aria-describedby="ariaDescribedby" name="some-radios" value="B">Option B</b-form-radio>
          </b-form-group>
          <div class="mt-3">Selected: <strong>{{ selected }}</strong></div>
        <br>
       <div>
          <b-form-select v-model="selectedOpt" :options="options"></b-form-select>
          <div class="mt-3">Selected: <strong>{{ selectedOpt }}</strong></div>
        </div>
      </div>
      <div>
           <b-button-group>
              <!-- <save-button :validationConfiguration="validationConfiguration" :record="selected_record" @sendSave="saveForm" /> -->
              <!-- <b-button variant="success" @click="saveForm">Save</b-button> -->
              <!-- <delete-button :disabled="!selected_record.id" @delete="deleteRecord" /> 
              <b-button variant="warning" @click.prevent="clearAll">Clear</b-button> -->
           </b-button-group>
      </div>
           <br>
           <br>
    </b-col>
  </b-row>
  </div>
</b-container>
</template>

<script>
import jspdf from 'jspdf'

export default {
  name: 'PdfTest',
  props: {
    msg: String
  },
  data: () => {
    return {
      selected: '',
      selectedOpt: '',
      name: '',
      address: '',
      description: '',
      dismissSecs: 5,
      dismissCountDown: 0,
      options: [
          { value: null, text: 'Please select an option' },
          { value: '1 Opt', text: 'This is First option' },
          { value: '2 Opt', text: 'Selected Option' },
          { value: { 3: '3 Opt' }, text: 'This is an option with object value' },
          { value: '4 Opt', text: 'This one is disabled', disabled: true }
        ]
    }
  },
  methods: {
    downLoad() {

    },
    makePdf() {
      this.showAlert();// alert('PDF Downloading Please wait...')
      console.log('Making PDF');
      const doc = new jspdf();
      doc.text(this.name, 15,15);
      doc.save(this.name +'.pdf');
    },
    countDownChanged(dismissCountDown) {
      this.dismissCountDown = dismissCountDown
    },
    showAlert() {
        // console.log('Show Alert');
        this.dismissCountDown = this.dismissSecs
      }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
