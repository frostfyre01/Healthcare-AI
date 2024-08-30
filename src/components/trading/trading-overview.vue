<template>
   <div class="container">
        <div class="section">
            <h2>Overview</h2>
            <p>This summer, I took part in a high school stock trading competition, where I had the opportunity to delve into the world of stock trading with a fresh perspective. By leveraging the data analytics skills I learned from MIT BWSI, I was able to implement several trading strategies, which allowed me to explore and understand the nuances of rule-based trading more deeply. This experience not only enhanced my analytical skills but also provided valuable insights into how systematic approaches can influence trading outcomes. I was thrilled to apply theoretical knowledge in a practical setting and gain hands-on experience. </p>
            <p>In light of this experience, I'm sharing the detailed analysis of the data-driven approach I employed, the specific trading rules I implemented, and the outcomes achieved. I aim to offer insights and practical guidance for others interested in rule-based trading, while also reflecting on the effectiveness of different strategies in achieving competitive results.</p>
        </div>

        <div class="section">
            <h2>How Rule-based Trading Works</h2>
            <p>Stock trading is challenging for beginners due to the complexities of market analysis, emotional decision-making, and risk management. Understanding market trends, choosing the right stocks, and developing effective strategies can be overwhelming. Additionally, the emotional ups and downs and potential for losses can make trading stressful and difficult.</p>
            <p>Rule-based trading involves following predefined criteria for buying and selling assets. Traders set specific rules based on indicators or data, which dictate entry and exit points. This method minimizes emotional influence and ensures consistent, systematic decision-making for more predictable trading outcomes.</p>
        </div>

        <div class="section">
            <h2>Benefits</h2>
            <p>Here are a few benefits of rule-based trading:</p>
            <div style="margin-left: 30px;">
                <ul>
                    <li><b>Consistency:</b> <i>Adheres to predefined criteria, reducing emotional decision-making, avoiding impulsive trades.</i></li>
                    <li><b>Backtesting:</b> <i>Allows for evaluation of strategies using historical data.</i></li>
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
        this.$emit('change-tab', 'mystrategy');
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
</style>
  