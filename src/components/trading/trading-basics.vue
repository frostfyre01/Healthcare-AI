<template>
   <div class="container">
        <div class="section">
            <h2>Basics</h2>
            <p>The goal of a successful trading strategy is to achieve consistent profitability over time. Evaluating a trading strategy involves various factors. Here, I will focus on the fundamentals: Backtesting, Performance Metrics and Optimization.</p>
        </div>

        <div class="section">
            <h2>Backtesting</h2>
            <p>Backtesting is the process of testing a trading strategy using historical market data to evaluate its effectiveness and performance.</p>
        </div>

        <div class="section">
            <h2>Performance Metrics</h2>
            <p>Here are some key metrics for evaluating a strategy:</p>
            <div style="margin-left: 30px;">
                <ul>
                    <li>Return on Investment (ROI): Measures the percentage gain or loss relative to the initial investment.</li>
                    <li>Gross Profit: the sum of all profits from winning trades.</li>
                    <li>Gross Loss: the sum of all losses from losing trades.</li>
                    <li>Profit Factor: The ratio of gross profits to gross losses, indicating overall profitability.</li>
                    <li>Maximum Drawdown: Indicates the largest peak-to-trough decline in equity during a specific period.</li>
                    <li>Total Trade Number: The count of all executed trades within a specific period, reflecting trading activity.</li>
                    <li>Win/Loss Ratio: Compares the number of winning trades to losing trades.</li>
                    <li>Average Trade Profit/Loss: Calculates the average profit or loss per trade.</li>
                </ul>
            </div>
        </div>

        <div class="section">
            <h2>Optimization</h2>
            <p>Adjust and refine the strategy parameters to improve performance, but avoid overfitting to historical data, which can lead to poor future performance.</p>
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
  