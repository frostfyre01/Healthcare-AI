<template>
   <div class="container">
        <div class="section">
            <h2>Performance Metrics</h2>
            <p>The goal of a successful trading strategy is to achieve consistent profitability over time. Evaluating a trading strategy involves various factors. I will only focus on the fundamentals:</p>
            <div style="margin-left: 30px;">
                <ul>
                    <li><b>Return on Investment (ROI):</b> <i>Measures the percentage gain or loss relative to the initial investment.</i></li>
                    <li><b>Gross Profit:</b> <i>the sum of all profits from winning trades.</i></li>
                    <li><b>Gross Loss:</b> <i>the sum of all losses from losing trades.</i></li>
                    <li><b>Profit Factor:</b> <i>The ratio of gross profits to gross losses, indicating overall profitability.</i></li>
                    <li><b>Maximum Drawdown:</b> <i>Indicates the largest peak-to-trough decline in equity during a specific period.</i></li>
                    <li><b>Total Trade Number:</b> <i>The count of all executed trades within a specific period, reflecting trading activity.</i></li>
                    <li><b>Win/Loss Ratio:</b> <i>Compares the number of winning trades to losing trades.</i></li>
                    <li><b>Average Trade Profit/Loss:</b> <i>Calculates the average profit or loss per trade.</i></li>
                </ul>
            </div>
        </div>

        <div class="section">
            <h2>Backtesting Essentials</h2>
            <p>To effectively evaluate a trading strategy, it’s important to use ample historical data covering diverse market conditions. Generating a sufficient number of trades within this data ensures that the results are statistically significant and reflective of various market scenarios.</p>
        </div>

        <div class="section">
            <h2>Profitability</h2>
            <p>A <b>profit factor</b> greater than 1 indicates that the strategy generates more profit than loss, while a profit factor below 1 suggests that losses outweigh profits. A higher profit factor signifies a more favorable risk-to-reward ratio.</p>
            <img src="@/assets/images/profit_factor.png">
            <p><b>Win Rate</b> represents the percentage of winning trades out of the total number of trades executed over a given period.</p>
            <img src="@/assets/images/win_rate.png">
            <p>A high win rate indicates that a trading strategy has a higher proportion of winning trades compared to losing trades. While this suggests that the strategy is effective at identifying profitable opportunities. However it does not necessarily guarantee overall profitability. </p>
            <p>For example:
                <div class="code">
                    <ul style="margin-left: 30px;">
                        <li>Winning Trades: 8 trades, each with an average profit of $50.</li>
                        <li>Losing Trades: 2 trades, each with an average loss of $300.</li>
                        <li>Win Rate = 80%, Total Profit = -$200 (net loss)</li>
                    </ul>
                </div>                    
            </p>
            <p>Some strategies may have a low win rate but achieve high profitability by ensuring that the wins are significantly larger than the losses.</p>
            <div class="code">
                When a trading strategy shows a low win rate yet remains profitable, it is essential to determine whether the success is attributable to random chance or a solid underlying strategy. Key challenges include frequent drawdowns and psychological stress.
            </div>
            <p><b>Quick Summary:</b> With a profit pactor of 2.3 and a 65% win rate over the past 10 years, based on enough number of trades, this strategy appears effective, with good profitability and a high rate of successful trades.</p>
            <img src="@/assets/images/result_spy_xyld.png">
        </div>

        <div class="section">
            <h2>Return on Investment (ROI)</h2>
            <p>When calculating ROI, the Annual Percentage Rate (APR) is typically used. This strategy has achieved an annual rate of 10.9% over the past 10 years. Additionally, it's important to consider factors such as the equity curve and drawdowns. Ideally, the equity curve should exhibit a consistent upward trend, and significant drawdowns should be minimized.</p>
            <img src="@/assets/images/equity_spy_xyld.png">
            <p>When applying <b>linear regression</b> to the equity curve, the observed upward slope suggests that the strategy is likely to remain profitable over time.</p>            
        </div>        

        <div class="section">
            <h2>Trade Profit Percentage</h2>
            <p></p>
            <img src="@/assets/images/score_spy_xyld.png">
        </div>

        <div class="section">
            <h2>Return on Investment (ROI)</h2>
            <p>Ready to elevate your trading game? Follow the link below to get started with our trading strategy and discover how it can transform your trading experience.</p>
            <v-btn color="primary" @click="handleButtonClick">Learn More</v-btn>
        </div>

    </div>
</template>
  
<script>
export default {
  methods: {
    handleButtonClick() {
        this.$emit('change-tab', 'basics');
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
  