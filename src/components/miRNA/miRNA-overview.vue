<template>
   <div class="container">
        <div class="section">
            <h2>Overview</h2>
            <p>This summer, I participated in a high school stock trading competition, which gave me the chance to explore the world of stock trading from a fresh perspective. By leveraging my data analytics skills, I implemented several trading strategies, allowing me to delve deeper into the nuances of rule-based trading. This experience not only improved my analytical skills but also offered valuable insights into how systematic approaches can impact trading outcomes. I applied my newly developed strategies in the competition and won first place, earning a $600 award out of over 300 participants.</p>
            <p>In light of this experience, I'm sharing the detailed analysis of the data-driven approach I employed, the specific trading rules I implemented, and the outcomes achieved. I aim to offer insights and practical guidance for those interested in rule-based trading, while also reflecting on the effectiveness of different trading strategies in actual market conditions.</p>
        </div>

        <div class="section">
            <h2>What is microRNA</h2>
            <p>A <b>biomarker</b> is a biological characteristic that can be measured and evaluated as an indicator of a normal or abnormal process, or a response to a therapeutic intervention. Biomarkers can be molecules, genes, or other biological substances found in blood, tissues, or other bodily fluids.</p>
            <p><b>microRNA (miRNA)</b> is a type of RNA found in cells and in blood. miRNA are smaller than many other types of RNA and can bind to messenger RNAs (mRNAs) to block them from making proteins. As of now, there are over 2,500 identified human microRNAs.</p>
            <p>miRNAs can be used as biomarkers for cancer detection. Altered expression levels of specific miRNAs have been associated with various types of cancer, including breast, lung, colorectal, and prostate cancers. These changes can reflect the presence of tumors, tumor progression, and response to treatment.</p>
        </div>

        <div class="section">
            <h2>Benefits</h2>
            <p>miRNAs can be detected in body fluids such as blood, serum, and urine, which makes them convenient for non-invasive testing. Their stability in these fluids adds to their appeal as potential biomarkers for early detection, diagnosis, and monitoring of cancer.</p>
        </div>

        <div class="section">
            <v-btn color="primary" @click="handleButtonClick">Learn More</v-btn>
        </div>
    </div>
</template>
  
<script>
export default {
  methods: {
    handleButtonClick() {
        this.$emit('change-tab', 'data');
    }
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
  