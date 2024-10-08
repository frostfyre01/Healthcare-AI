<template>
   <div class="container">
        <div class="section">
            <h2>Accuracy</h2>
            <p>This summer, I participated in a high school stock trading competition, which gave me the chance to explore the world of stock trading from a fresh perspective. By leveraging my data analytics skills, I implemented several trading strategies, allowing me to delve deeper into the nuances of rule-based trading. This experience not only improved my analytical skills but also offered valuable insights into how systematic approaches can impact trading outcomes. I applied my newly developed strategies in the competition and won first place, earning a $600 award out of over 300 participants.</p>
            <p>In light of this experience, I'm sharing the detailed analysis of the data-driven approach I employed, the specific trading rules I implemented, and the outcomes achieved. I aim to offer insights and practical guidance for those interested in rule-based trading, while also reflecting on the effectiveness of different trading strategies in actual market conditions.</p>
        </div>
        <img src="@/assets/images/miRNA/mirna-accuracy.png">

        <div class="section">
            <h2>Confusion Matrix</h2>
            <p>This summer, I participated in a high school stock trading competition, which gave me the chance to explore the world of stock trading from a fresh perspective. By leveraging my data analytics skills, I implemented several trading strategies, allowing me to delve deeper into the nuances of rule-based trading. This experience not only improved my analytical skills but also offered valuable insights into how systematic approaches can impact trading outcomes. I applied my newly developed strategies in the competition and won first place, earning a $600 award out of over 300 participants.</p>
            <p>In light of this experience, I'm sharing the detailed analysis of the data-driven approach I employed, the specific trading rules I implemented, and the outcomes achieved. I aim to offer insights and practical guidance for those interested in rule-based trading, while also reflecting on the effectiveness of different trading strategies in actual market conditions.</p>
        </div>
        <img src="@/assets/images/miRNA/mirna-matrix.png">

        <div class="section">
            <h2>Receiver Operating Characteristic (ROC) curve</h2>
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

        <img src="@/assets/images/miRNA/mirna-roc.png">

        <div class="section">
            <v-btn color="primary" @click="handleButtonClick">Learn More</v-btn>
        </div>
    </div>
</template>
  
<script>
export default {
  methods: {
    handleButtonClick() {
        this.$emit('change-tab', 'application');
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
  