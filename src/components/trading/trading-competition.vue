<template>
   <div class="container">
        <div class="section">
            <h2>More Strategies</h2>
            <p>Before entering the stock trading competition, I created several new trading strategies based on the same trading logic, focusing mainly on highly correlated stock ETFs. Most of these strategies produced comparable results, with a Profit Factor (PF) exceeding 2.5 and a win rate above 65%. This supports the effectiveness of the trading logic and has significantly boosted my confidence in the strategy.</p>
            <p>Here, I have included two equity curves and the Annualized Rate of Return (ARR).</p>
            <img src="@/assets/images/trading/equity_qqq_qyld.png">
            <p></p>
            <img src="@/assets/images/trading/equity_iwm_spy.png">
        </div>

        <div class="section">
            <h2>Stock Trading Competition</h2>
            <img src="@/assets/images/trading/competition.png">
            <p>Once the stock trading competition starts, I can simply run all the trading strategies before the market closes each day to check for any signals to trade, thanks to the rule-based trading approach.</p>
            <p>Using the newly developed trading strategies, I achieved a <b>17%</b> profit over a 2-month period and won first place. During the same period, the benchmark broad market index fund gained less than 4%.</p>
        </div>

        <div class="section">
            <h2>Takeaways</h2>
            <p>This experience provided a valuable lesson on how systematic approaches can enhance stock trading results. I was thrilled to apply theoretical knowledge in a real-world trading environment and gain practical experience. I recognize that there are many areas for improvement in the strategy, including entry, exit, and position management. There are numerous systematic approaches available to refine these aspects.</p>
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
  