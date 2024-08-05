<template>
  <v-container>
    <div class="text-Left">
      <div class="text-body-4 font-weight-light mb-n1"><v-icon>mdi-dna</v-icon>miRNA</div>
      <h2 class="text-h4 font-weight-black">Lung cancer detection</h2>
      <hr/>
      <br/>
    </div>

    <v-stepper :items="['Overview', 'Data', 'Biomaker', 'Model', 'Metrics', 'Application']">

      <template v-slot:item.1>
          <div>
            <ul>
              <li><strong>Lung cancer:</strong> Lung cancer remains one of the leading causes of cancer-related deaths globally. Early detection significantly improves survival rates and treatment outcomes.</li>
              <li><strong>Traditional detection methods:</strong> Include chest X-rays, computed tomography (CT) scans, and biopsy procedures. These methods are typically invasive, have varying sensitivity and specificity, and may detect cancer at a later stage.</li>
            </ul>
            <hr style="width: 80%; margin: 20px auto;">
            <ul>
              <li><strong><v-icon color="blue">mdi-dna</v-icon>MicroRNAs (miRNAs):</strong> Small non-coding RNAs that regulate gene expression.</li>
              <li><strong>Project goal:</strong> Develop a non-invasive diagnostic tool using miRNA profiling for early detection.</li>
            </ul>
          </div>
      </template>

      <template v-slot:item.2>
        <v-card title="Data" flat>How do I get the data</v-card>
      </template>

      <template v-slot:item.3>
        <v-card title="Biomaker" flat>...</v-card>
      </template>

      <template v-slot:item.4>
        <v-card title="Model" flat>...</v-card>
      </template>

      <template v-slot:item.5>
        <v-card title="Model Evaluation And Metrics" flat>...</v-card>
      </template>

      <template v-slot:item.6>
        <v-card title="Application" flat>...</v-card>
      </template>


    </v-stepper>
  </v-container>
</template>

<script>

</script>

<style scoped>
  ul {
    list-style-type: disc;
    margin-left: 20px;
  }
</style>
