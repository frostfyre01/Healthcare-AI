<template>
   <div class="container">
        <div class="section">
            <h2>More Strategies</h2>
            <p>Before entering the stock trading competition, I created several new trading strategies based on the same trading logic, focusing mainly on highly correlated Index ETFs and stocks, such like Master Card(MA) and Visa(V). Most of these strategies produced comparable results, with a Profit Factor (PF) exceeding 2.5 and a win rate above 65%. This supports the effectiveness of the trading logic. Here, I have included a few equity curves and the Annualized Rate of Return (ARR).</p>
            <img src="@/assets/images/trading/equity_qqq_qyld.png">
            <p></p>
            <img src="@/assets/images/trading/equity_iwm_spy.png">
            <p></p>
            <img src="@/assets/images/trading/equity_ma_v.png">
        </div>

        <div class="section">
            <h2>Stock Trading Competition</h2>
            <img src="@/assets/images/trading/competition.png">
            <p>For the stock trading competition, over 300 high school students each receive $1,000,000 in virtual funds to invest using a simulator with real-time pricing data. Trading begins on June 4, 2024, and ends on July 26, 2024.</p>
            <p>Using the newly developed trading strategies, I achieved a <b>17% profit</b> over a 2-month period and won first place. During the same period, the benchmark broad market index fund SPY gained less than 4%.</p>
        </div>

        <div class="section">
            <h2>Takeaways</h2>
            <p>The trading strategy I demonstrated is an extremely simplified and unpolished version. I recognize that there are many areas for improvement, including entry, exit, and position management—each of which requires a deep understanding of trading. However, it provides a baseline upon which we can build, compare, and refine further.</p>
            <p>The most valuable knowledge I gained is understanding how to evaluate a trading system. With numerous indicators available for stock trading, I now have a systematic approach to determine which ones perform best under various market conditions and to understand the trading logic behind these indicators. This insight will aid in decision-making and help stabilize trading outcomes. I was thrilled to apply theoretical knowledge in a real-world trading environment and gain practical experience.</p>
            <p>Looking ahead, this approach will incorporate not only traditional data analytics but also machine learning techniques such as <b>Reinforcement Learning (RL)</b>, further enhancing the evaluation process.</p>
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
  