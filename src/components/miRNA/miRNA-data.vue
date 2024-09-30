<template>
   <div class="container">
        <v-alert type="info" border="left" prominent>
            Please use the following link to access the Jupyter Notebook:
            <v-btn text @click="openLink" class="ml-2">Open Notebook</v-btn>
        </v-alert>
        <div class="section">
            <h2>Data Source</h2>
            <p>The <b>National Institutes of Health (NIH)</b> offers a vast array of research studies, clinical trials, and reviews on biomarkers, including microRNAs.</p>
            <p>By searching relevant terms on <a href="https://www.ncbi.nlm.nih.gov/" target="_blank">NIH.gov</a> we can find many articles that detail the methods, outcomes, and importance of using microRNAs in blood tests for cancer diagnosis. Here are a few examples:</p>
            <ul style="margin-left: 30px;">
                <li><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE137140" target="_blank">Lung Cancer Dataset</a></li>
                <li><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE164174" target="_blank">Gastric Cancer Dataset</a></li>
                <li><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE122497" target="_blank">Esophageal Dataset</a></li>
                <li><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE113486" target="_blank">Bladder Cancer Dataset</a></li>
            </ul>
        </div>

        <div class="section">
            <h2>Data Structure</h2>
            <p>miRNA readings consist of fields like miRNA names, expression levels, clinical data, and patient identifiers. Here is a sample of the data for lung cancer.</p>
        </div>
        <img src="@/assets/images/miRNA/mirna-data.png" />

        <div class="section">
            <h2>Data Processing</h2>
            <p>Before creating a model, several data processing steps should be performed, including:</p>
            <ul style="margin-left: 30px">
                <li><b>Data Cleaning:</b> Remove duplicates, handle missing values, and correct errors.</li>
                <li><b>Data Transformation:</b> Normalize or standardize data to ensure consistency.</li>
                <li><b>Encoding Categorical Variables:</b> Convert categorical data into numerical format if necessary.</li>
            </ul>
        </div>
        <img src="@/assets/images/miRNA/mirna-class.png" />

        <div class="section">
            <h2>Feature Selection</h2>
            <p>Identify and select relevant features that contribute to the model.</p>
        </div>
        <img src="@/assets/images/miRNA/mirna-hue.png" />

        <div class="section">
            <v-btn color="primary" @click="handleButtonClick">Learn More</v-btn>
        </div>
    </div>
</template>
  
<script>
export default {
  methods: {
    handleButtonClick() {
        this.$emit('change-tab', 'model');
    },
    openLink() {
      window.open('https://deepnote.com/app/healthcare-ai-web/miRNA-cancer-detection-8bcf6c22-7a5a-48dc-85d6-e976abbf3aaa', '_blank');
    },
  }
}
</script>
  
<style scoped>
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
    color: #333;
}
.container {
    width: 80%;
    margin: 0; /* Removed auto margin for center alignment */
    padding: 20px;
    margin-left: 0;
    margin-right: auto;
}
header {
    background: #007bff;
    color: #fff;
    padding: 10px 0;
    text-align: center;
}
h1 {
    margin: 0;
}
.section {
    margin: 20px 0;
}
.section h2 {
    border-bottom: 2px solid #007bff;
    padding-bottom: 10px;
}
.section p {
    margin: 10px 0;
}
.code {
    font-family: 'Courier New', Courier, monospace;
    background-color: rgb(238, 255, 240);
    padding: 5px;
    border: 1px solid #ccc;
    border-radius: 5px;
}
</style>
  