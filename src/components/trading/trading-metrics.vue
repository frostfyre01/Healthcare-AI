<template>
   <div class="container">
        <v-alert type="info" border="left" prominent>
            Please use the following link to access the Jupyter Notebook:
            <v-btn text @click="openLink" class="ml-2">Open Notebook</v-btn>
            <v-btn text @click="downloadNotebook('SPY_Analysis.ipynb')" class="ml-2">Download Notebook</v-btn>
        </v-alert>

        <div class="section">
            <h2>Performance Metrics</h2>
            <p>The goal of a successful trading strategy is to achieve consistent profitability over time. Evaluating a trading strategy involves various factors. I will only focus on the fundamentals:</p>
            <div style="margin-left: 30px;">
                <ul>
                    <li><b>Total Trade Number:</b> <i>The count of all executed trades within a specific period, reflecting trading activity.</i></li>
                    <li><b>Gross Profit:</b> <i>the sum of all profits from winning trades.</i></li>
                    <li><b>Gross Loss:</b> <i>the sum of all losses from losing trades.</i></li>
                    <li><b>Profit Factor:</b> <i>The ratio of gross profits to gross losses, indicating overall profitability.</i></li>
                    <li><b>Win/Loss Ratio:</b> <i>Compares the number of winning trades to losing trades.</i></li>
                    <li><b>Return on Investment (ROI):</b> <i>Measures the percentage gain or loss relative to the initial investment.</i></li>
                    <li><b>Maximum Drawdown:</b> <i>Indicates the largest peak-to-trough decline in equity during a specific period.</i></li>
                    <li><b>Average Trade Profit/Loss:</b> <i>Calculates the average profit or loss per trade.</i></li>
                </ul>
            </div>
        </div>

        <div class="section">
            <h2>Total Trade Number</h2>
            <p>To effectively evaluate a trading strategy, it's crucial to use ample historical data that covers diverse market conditions. Generating a sufficient number of trades within this data helps ensure that the results are statistically significant and reflective of various market scenarios. My back-testing results, which contain 100+ trades, represent a solid starting point for evaluating a trading strategy, particularly for small-scale studies.</p>
        </div>

        <div class="section">
            <h2>Profitability</h2>
            <p>A <b>profit factor</b> greater than 1 indicates that the strategy generates more profit than loss, while a profit factor below 1 suggests that losses outweigh profits. A higher profit factor signifies a more favorable risk-to-reward ratio.</p>
            <img src="@/assets/images/trading/profit_factor.png">
            <p><b>Win Rate</b> represents the percentage of winning trades out of the total number of trades executed over a given period.</p>
            <img src="@/assets/images/trading/win_rate.png">
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
                When a trading strategy exhibits a low win rate but remains profitable, it is crucial to determine whether the success is due to random chance (luck) or a solid underlying strategy. Additionally, managing frequent drawdowns and psychological stress presents a significant challenge.
            </div>
            <p>This strategy yields the following results:</p>
            <p><img src="@/assets/images/trading/result_spy_xyld.png"></p>
            <p>With a profit pactor of 3.0 and a 72% win rate over the past 10 years, based on enough number of trades, this strategy appears effective, with good profitability and a high rate of successful trades.</p>
            
        </div>

        <div class="section">
            <h2>Return on Investment (ROI)</h2>
            <p>When calculating ROI, the <b>Annualized Rate of Return (ARR)</b> is typically used. This strategy has achieved an annual rate of 12.4% over the past 10 years. Additionally, it's important to consider factors such as the equity curve and drawdowns. Ideally, the equity curve should exhibit a consistent upward trend, and significant drawdowns should be minimized.</p>
            <img src="@/assets/images/trading/equity_spy_xyld.png">
            <p>When applying <b>linear regression</b> to the equity curve, the observed upward slope suggests that the strategy is likely to remain profitable over time.</p>            
        </div>        

        <div class="section">
            <h2>Trade Profit Percentage</h2>
            <p>Trade Profit Percentage is calculated as:</p>
            <img src="@/assets/images/trading/trade_percent.png">
            <p>Ideally, the trade profit percentage should be evenly distributed to ensure consistent performance and reduce volatility, balancing gains and losses effectively.Extremely large profits or losses are not favorable as they introduce significant volatility and risk, making it harder to maintain consistent performance and manage overall trading strategy effectively.</p>
            <img src="@/assets/images/trading/score_spy_xyld.png">
            <p><b>Calculate Expected Return:</b> The expected return of the strategy can be computed using the formula:</p>
            <div class="code">
                Expected Return = (Win Rate × Average Profit Percentage) − (Loss Rate × Average Loss)
            </div>
            <div class="code">
                Expected Return = (0.72 × 2.68%) − (0.28 × 2.32%) = 1.28%
            </div>
            <p><i>This indicates that the strategy is projected to yield an average return of around +1.28% per trade. With a win rate of 72%, it offers a favorable risk/reward ratio, as the average gain exceeds the average loss.</i></p>
        </div>

        <div class="section">
            <h2>Summary</h2>
            <p>This simple trading strategy has shown good performance over the last decade. It has a <b>Profit Factor of 3.0</b>, meaning it earns more than three times as much from winning trades compared to losing trades. The strategy has a higher success rate than its loss rate. It <b>wins 72%</b> of the time.<b>On average, each trade yields a return of 1.28%</b>. The <b>104 trades</b> are evenly distributed, which helps in managing risk and avoiding large losses. Importantly, there are <b>no significant drawdowns</b>, indicating stable performance without major drops in equity. Overall, the strategy appears to be both profitable and reliable.</p>
            <p>We’ll see how it performs against new, untested data in a real-world stock trading competition.</p>            
            <v-btn color="primary" @click="handleButtonClick">Learn More</v-btn>
        </div>

        <div class="section">
            <h2>Further Notes</h2>
            <p>Although the strategy's annual return of 12.4% is slightly lower than the buy-and-hold return of SPY, it presents a much lower risk profile. </p>
            <img src="@/assets/images/trading/spy.png">
            <p>When comparing the equity curve to SPY's price, we observe that SPY experienced maximum drawdowns of -30% in 2020 and -25% in 2022. In contrast, the maximum drawdown for this strategy was about <b>-7%</b>. This suggests that trading with the strategy has significantly lower risk compared to buy-and-hold SPY. To potentially boost overall returns, we could consider using leverage, which may increase both risk and return.</p>
        </div>

    </div>
</template>
  
<script>
export default {
  methods: {
    handleButtonClick() {
        this.$emit('change-tab', 'competition');
    },
    openLink() {
      window.open('https://deepnote.com/app/healthcare-ai-web/Stock-trading-analysis-project-a1dba5c8-7531-4272-828d-1fa518690a99', '_blank');
    },
    downloadNotebook(fileName) {
        const notebookUrl = '/downloads/' + fileName;
        const link = document.createElement('a');
        link.href = notebookUrl;
        link.download = fileName;
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
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
  