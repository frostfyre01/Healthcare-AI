<template>
   <div class="container">
        <div class="section">
            <h2>Trade Logic</h2>
            <p>Start by identifying pairs of stocks with a high historical correlation, meaning their prices typically move in the same direction and by similar magnitudes. However, since markets are imperfect, there may be instances where these stocks diverge from their usual correlation patterns. These deviations can present trading opportunities, as prices are likely to revert to their typical correlation range over time. This approach is referred to as <b>Mean Reversion</b>.</p>
        </div>

        <div class="section">
            <h2>How It Works</h2>
            <p>For example, consider the pair of <b>SPY</b> (S&P 500 ETF) and <b>XYLD</b> (Global X S&P 500 Covered Call ETF). Both SPY and XYLD are correlated since they are both based on the S&P 500 Index. However, the covered call strategy employed by XYLD can cause its performance to diverge slightly from SPY, depending on market conditions.</p>
            <p>To measure this divergence, I use the <b>Rate of Change (ROC)</b> indicator and calculate the ROC difference between the two stocks, using this difference as an entry signal.</p>
            <p><b>Rate of Change (ROC)</b> measures the percentage change in price over a specified period, helping to assess the speed and direction of price movements. It is calculated as:</p>
            <pre style="color: red;">ROC = [(Current Price - Price N Periods Ago) / Price N Periods Ago] × 100</pre>
        </div>

        <div class="section">
            <h2>Trading Rules</h2>
            <P><b>Entry Signal:</b> Monitor the ROC difference, with an ROC difference below -4% potentially signaling a buying opportunity.</P>
            <p><b>Exit Signal:</b> To simplify the process, I use two fixed exit strategies and exit the position when either condition is met.</p> 
            <p><b>Exit #1</b> <i>When: profit hits a predefined target level, such as +5%</i></p> 
            <p><b>Exit #2</b> <i>When: the position has been held for more than 10 days</i></p>        
            <p><b>Interpretation:</b> <i>Historically, the average ROC difference ranges between -3% and +3%. A significant divergence, such as an ROC difference below -4%, may indicate an anomaly or temporary market inefficiency, suggesting that SPY is underperforming relative to XYLD compared to their typical relationship. This deviation might suggest that SPY is undervalued, presenting a buying opportunity. Once a position is established, we aim to sell it at a +5% profit. If this target isn’t reached within a set period, we will exit the position, regardless of the outcome, whether a gain or a loss, and wait for the next signal.</i></p>
        </div>

        <div class="section">
            <h2>Rules</h2>
            <p>Ready to elevate your trading game? Follow the link below to get started with our trading strategy and discover how it can transform your trading experience.</p>
            <v-btn color="primary" @click="handleButtonClick">Learn More</v-btn>
        </div>
    </div>
</template>
  
<script>
export default {
  methods: {
    handleButtonClick() {
        this.$emit('change-tab', 'metrics');
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
  