<template>
   <div class="container">
        <div class="section">
            <h2>Trade Logic</h2>
            <p>My strategy uses the <b>Mean Reversion</b> approach. Start by identifying pairs of stocks with a high historical correlation, where their prices usually move together in the same direction and by similar magnitudes. Since markets are imperfect, deviations from this correlation can occur. These deviations present trading opportunities, as prices are expected to revert to their typical correlation range over time.</p>
        </div>

        <div class="section">
            <h2>How It Works</h2>
            <p>For example, consider the pair of <b>SPY</b> (S&P 500 ETF) and <b>XYLD</b> (Global X S&P 500 Covered Call ETF). Both SPY and XYLD are correlated since they are both based on the S&P 500 Index. However, the covered call strategy employed by XYLD can cause its performance to diverge slightly from SPY, depending on market conditions.</p>
            <p>To measure this divergence, I use the <b>Rate of Change (ROC)</b> indicator and calculate the ROC difference between the two stocks, using this difference as an entry signal.</p>
            <p><b>Rate of Change (ROC)</b> measures the percentage change in price over a specified period, helping to assess the speed and direction of price movements. It is calculated as:</p>
            <pre class="code">ROC = [(Current Price - Price N Periods Ago) / Price N Periods Ago] × 100</pre>
            <div class="example">
                <p>For example:</p>
                <p>If the current price of SPY is $55 and the price 20 days ago was $50, then the ROC can be calculated using the following formula:</p>
                <div class="code">
                    ROC = <strong>100 * (55 - 50) / 50</strong> = 10%
                </div>
            </div>
            <p><b>ROC difference</b> is calculated as:</p>
            <pre class="code">ROC difference = ROC(SPY) - ROC(XYLD)</pre>
        </div>

        <div class="section">
            <h2>Trading Rules</h2>
            <P><b>Entry Signal:</b> When an ROC difference below -4% potentially signaling a buying opportunity.</P>
            <p><b>Exit Signal:</b> I use two fixed exit strategies and exit the position when either condition is met.</p> 
            <p><b>Exit #1</b> <i>When: profit hits a predefined target level, such as +5%</i></p> 
            <p><b>Exit #2</b> <i>When: the position has been held for more than 10 days</i></p>        
            <p><i>Notes: The parameters provided are examples only; we will optimize them during the evaluation process.</i></p>
            <p><b>Interpretation:</b> <i>Historically, the average ROC difference ranges between -3% and +3%. A significant divergence, such as an ROC difference below -4%, may indicate an anomaly or temporary market inefficiency, suggesting that SPY is underperforming relative to XYLD compared to their typical relationship. This deviation might suggest that SPY is undervalued, presenting a <b>buying</b> opportunity. Once a position is established, we aim to <b>sell</b> it at a +5% profit. If this target isn’t reached within a set period, we will <b>exit/close</b> the position, regardless of the outcome, whether a gain or a loss, and wait for the next signal.</i></p>

        </div>

        <div class="section">
            <h2>Validation</h2>
            <p>Once the trading rule is defined, it's crucial to use back-testing to thoroughly validate the strategy’s potential profitability and effectiveness. This ensures that the strategy performs well under historical market conditions before implementation.</p>
            <v-btn color="primary" @click="handleButtonClick">Learn More</v-btn>
        </div>
    </div>
</template>
  
<script>
export default {
  methods: {
    handleButtonClick() {
        this.$emit('change-tab', 'implement');
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
.example {
    background-color: #f9f9f9;
    border: 1px solid #ddd;
    padding: 10px;
    border-radius: 5px;
}
.code {
    font-family: 'Courier New', Courier, monospace;
    background-color: rgb(238, 255, 240);
    padding: 5px;
    border: 1px solid #ccc;
    border-radius: 5px;
}
</style>
  