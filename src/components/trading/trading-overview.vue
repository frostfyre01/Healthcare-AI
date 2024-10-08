<template>
   <div class="container">
        <div class="section">
            <h2>Overview</h2>
            <p>This summer, I participated in a national high school stock trading competition, which gave me the chance to explore the world of stock trading from a fresh perspective. By leveraging my data analytics skills, I implemented several trading strategies, allowing me to delve deeper into the nuances of rule-based trading. This experience not only improved my analytical skills but also offered valuable insights into how systematic approaches can impact trading outcomes. I applied my newly developed strategies in the competition and won first place, earning a $600 award out of over 300 participants.</p>
            <p>In light of this experience, I'm sharing the detailed analysis of the data-driven approach I employed, the specific trading rules I implemented, and the outcomes achieved. I aim to offer insights and practical guidance for those interested in rule-based trading, while also reflecting on the effectiveness of different trading strategies in actual market conditions.</p>
        </div>

        <div class="section">
            <h2>What is Rule-based Trading</h2>
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
            <h2>Trading Expectancy</h2>
            <p>Imagine a betting game where you place a $2 bet each time to draw a marble from a bag containing 6 red marbles and 4 black marbles. The rules are as follows:
                <ul style="margin-left: 30px;">
                    <li>If you draw a red marble, you win $3.</li>
                    <li>If you draw a black marble, you lose your $2 bet.</li>
                    <li>After each draw, the marble is placed back in the bag.</li>
                </ul>
            </p>
            <p><b>Probabilities:</b></p>
            <p>When playing this game, we can determine the following probabilities:
                <ul style="margin-left: 30px;">
                    <li>Probability of Drawing a Red Marble: P(Red) = 6/10 = 0.6</li>
                    <li>Probability of Drawing a Black Marble: P(Black) = 4/10 = 0.4</li>
                </ul>
            </p>
            <p>At first glance, this game appears to be favorable to play, as we have a higher chance of winning money. However, it’s important to consider the <b>expected value (EV)</b>, which reveals that, despite the seemingly good odds, players can still incur losses over time.</p>
            <p><b>Outcomes:</b>
                <ul style="margin-left: 30px;">
                    <li>If we draw a red marble: We win $3, but we need to account for our $2 bet.<br/>
                        <i>Net Gain: $3 - $2 = $1</i><br/>
                    </li>
                    <li>If we draw a black marble: We lose our $2 bet.<br/>
                        <i>Net Loss: -$2</i><br/>
                    </li>
                </ul>
            </p>
            <p>In this game, even though we have a higher probability of winning money, the expected value is negative.</p>
            <p class="code">Expected Value = (0.6 × 1) + (0.4 × (−2)) = 0.6 − 0.8 = −0.2<br/>
            The expected value of this betting game is −$0.20. This means that, on average, we would lose 20 cents per bet in the long run. Therefore, we should avoid this game, as we are more likely to incur losses rather than gains.
            </p>
            <p>By applying the same concept, when we analyze a trading system, we should focus on ensuring that the trading expectancy is positive. <b>Trading Expectancy</b> is calculated as:</p>
            <img src="@/assets/images/trading/expectancy.png">
            <p><b>Trading Expectancy</b> helps traders evaluate strategies by quantifying their performance. A positive expectancy indicates that the strategy is likely profitable over time, while a negative expectancy suggests potential losses and should generally be avoided.</p>
        </div>

        <div class="section">
            <h2>Design Flow</h2>
            <p>When designing a trading strategy, consider the following key steps:</p>
            <p>
                <ul style="margin-left: 30px;">
                    <li><b>Define Goals:</b> Set clear objectives, including target returns, risk tolerance, and time horizons.</li>
                    <li><b>Develop Trading Logic:</b> Choose indicators and rules for trade entries and exits.</li>
                    <li><b>Backtest Using Historical Data:</b> Test trading logic on historical data to create a trade list with entry and exit points.</li>
                    <li><b>Evaluate Performance:</b> Analyze results using metrics like profit factor, win/loss ratio, and drawdowns.</li>
                    <li><b>Adjust Parameters:</b> Refine strategy based on performance and re-test with adjusted parameters.</li>
                    <li><b>Implement and Monitor:</b> Apply the strategy in live trading and regularly review its performance, adjusting as needed.</li>
                </ul>
            </p>            
            <img src="@/assets/images/trading/design-flow.png">
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
.code {
    font-family: 'Courier New', Courier, monospace;
    background-color: rgb(238, 255, 240);
    padding: 5px;
    border: 1px solid #ccc;
    border-radius: 5px;
}
</style>
  