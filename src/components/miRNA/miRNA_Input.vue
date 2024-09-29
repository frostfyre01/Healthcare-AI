<template>
    <v-container>
      <v-row>
        <v-col cols="12" md="6">
          <v-text-field
            v-model="MIMAT0019776_Input"
            label="MIMAT0019776 Input"
            placeholder="Enter first value"
            outlined
          ></v-text-field>
        </v-col>
  
        <v-col cols="12" md="6">
          <v-text-field
            v-model="MIMAT0022259_Input"
            label="MIMAT0022259 Input"
            placeholder="Enter second value"
            outlined
          ></v-text-field>
        </v-col>
      </v-row>
  
      <v-row>
        <!-- Dropdown Menu -->
        <v-col cols="12" md="6">
          <v-select
            v-model="SNO_SelectedOption"
            :items="options"
            label="Select an Option"
            outlined
          ></v-select>
        </v-col>
      </v-row>
  
      <v-row>
        <!-- Submit Button -->
        <v-col>
          <v-btn @click="handleSubmit" color="primary">Submit</v-btn>
        </v-col>
      </v-row>
  
      <!-- Display Values -->
      <v-row>
        <v-col>
          <p>First Input Value: {{ MIMAT0019776_Input }}</p>
          <p>Second Input Value: {{ MIMAT0022259_Input }}</p>
          <p>Selected Option: {{ SNO_SelectedOption }}</p>
          <p>API Response: {{ apiResponse }}</p>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  import { ref } from 'vue';
  import SERVICE_CONFIG from '@/service_config'
  
  export default {
    setup() {
      const MIMAT0019776_Input = ref('');
      const MIMAT0022259_Input = ref('');
      const SNO_SelectedOption = ref(null);
      const apiResponse = ref('');
  
      // Options for the dropdown
      const options = ref([
        'GSE137140',
        'GSE164174',
        'GSE122497',
        'GSE113486',
      ]);
  
      const handleSubmit = async () => {
        try {
          // GET request to an pythonanywhere URL
          let url = SERVICE_CONFIG.MIRNA_PREDICATE_URL;
          url += "?s_no=" + SNO_SelectedOption.value;
          url += "&MIMAT0019776=" + MIMAT0019776_Input.value;
          url += "&MIMAT0022259=" + MIMAT0022259_Input.value;
          const response = await fetch(url);
          if (!response.ok) {
            throw new Error('Network response was not ok');
          }
          const data = await response.json();
          apiResponse.value = JSON.stringify(data); // Save API response
          console.log('API Response:', data);
        } catch (error) {
          console.error('Error fetching data:', error);
        }
  
        // Log form values
        console.log('MIMAT0019776 Input:', MIMAT0019776_Input.value);
        console.log('MIMAT0022259 Input:', MIMAT0022259_Input.value);
        console.log('Selected Option:', SNO_SelectedOption.value);
      };
  
      return {
        MIMAT0019776_Input,
        MIMAT0022259_Input,
        SNO_SelectedOption,
        options,
        apiResponse,
        handleSubmit,
      };
    },
  };
  </script>
  
  <style scoped>
  /* Custom styles (if needed) */
  </style>
  