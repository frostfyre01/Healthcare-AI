<template>
   <div class="container">
        <v-alert type="info" border="left" prominent>
            Please use the following link to access the Jupyter Notebook:
            <v-btn text @click="openLink" class="ml-2">Open Notebook</v-btn>
        </v-alert>
        <div class="section">
            <h2>Data Splitting</h2>
            <p>Divide the dataset into training, validation, and test sets.</p>
            <img src="@/assets/images/miRNA/data_split_diagram.png">
            <p>separates the shuffled data into training (20%) and test (80%) sets.</p>
        </div>

        <div class="section">
            <h2>Model Training</h2>
            <p>Stock trading is challenging for beginners due to the complexities of market analysis, emotional decision-making, and risk management. Understanding market trends, choosing the right stocks, and developing effective strategies can be overwhelming. Additionally, the emotional ups and downs and potential for losses can make trading stressful and difficult.</p>
            <p>Rule-based methods can assist in handling various trading challenges. Rule-based trading involves following predefined criteria for buying and selling assets. Traders set specific rules based on indicators or data, which determine entry and exit points. This approach reduces emotional influence and ensures consistent, systematic decision-making, leading to more predictable trading results.</p>
            <p>Here are a few benefits of rule-based trading:</p>
            <div style="margin-left: 30px;">
                <ul>
                    <li><b>Consistency:</b> <i>Adheres to predefined criteria, reducing emotional decision-making, avoiding impulsive trades.</i></li>
                    <li><b>Backtesting:</b> <i>Allows for the evaluation of strategies using historical data, enabling us to estimate the outcomes of trading under similar market conditions.</i></li>
                    <li><b>Efficiency:</b> <i>Automates trading decisions, saving time and effort.</i></li>
                </ul>
            </div>

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
        this.$emit('change-tab', 'metrics');
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
  