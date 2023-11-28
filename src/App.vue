<template>

  Here is the template 'Test'

  <div>ENTRY is {{ ENTRY }}</div> 

  <div>activityData is {{ activityData }}</div>

  <Test :prop1="testval"/>

  <Validation v-for="validationItem in validationResults" :validation-item="validationItem" validation-choices="validationChoices" />
  
  
</template>

<script>
import { ref } from 'vue';
import Test from './components/Test.vue'
import Validation from './components/Validation.vue'

var blah = "a variable named blah";

var ENTRY = window.ENTRY;

export default {
  name: 'App',
  components: {
    Test, Validation
  },
  setup() {

    //Choices to be presented in validation
    const validationChoices = ['Yes','No','Pending','N/A'];
 
    const validationResults = [ { 'section':'LEGAD', 'selection':'Yes' },  { 'section':'SNR', 'selection':'Yes' } ];

 

  console.log("ENTRY:", ENTRY)

    return {blah, ENTRY, validationChoices, validationResults }
    

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


  background-color: #FFF;
  width: 700px;
  height: 550px;
}


</style>
