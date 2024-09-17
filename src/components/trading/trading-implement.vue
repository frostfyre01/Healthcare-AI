<template>
   <div class="container">
        <v-alert type="info" border="left" prominent>
            Please use the following link to access the Jupyter Notebook:
            <v-btn text @click="openLink" class="ml-2">Open Notebook</v-btn>
            <v-btn text @click="downloadNotebook('SPY_Analysis.ipynb')" class="ml-2">Download Notebook</v-btn>
        </v-alert>

        <div class="section">
            <h2>Correlation</h2>
            <p>First, let's examine the correlation between <b>SPY</b> and <b>XYLD</b>. The historical data for the past 10 years is downloaded and combined into a single DataFrame. The .corr() function is then used to calculate the correlation. As expected, SPY and XYLD demonstrate a very high correlation.</p>
            <div class="code">
                corr_matrix = df.corr()
            </div>                            
            <div class="code">
                correlation = df['SPY_Change'].corr(df['XYLD_Change'])
            </div>            
            <img src="@/assets/images/trading/correlation_spy_xyld.png">
        </div>

        <div class="section">
            <h2>Calculate Rate of Change</h2>
            <div class="code">
                <p>df['SPY_shifted'] = df['SPY'].shift(shift_down_value)</p>
                <p>df['SPY_ROC'] = (df['SPY'] - df['SPY_shifted']) / df['SPY_shifted']</p>
                <p>df['ROC_Difference'] = df['SPY_ROC'] - df['XYLD_ROC']</p>
            </div>            
            <img src="@/assets/images/trading/roc_spy_xyld.png">
        </div>

        <div class="section">
            <h2>Simulating Trades</h2>
            <p>Define the buy threshold, maximum number of position days, and target percentage, apply to the following trading rules:</p>
            <ul style="margin-left: 30px;">
                <li><b>Entry Criteria:</b> Buy when the ROC difference falls below the buy threshold.</li>
                <li><b>Exit Criteria #1:</b> Sell if the price rises by more than the target percentage from the entry price.</li>
                <li><b>Exit Criteria #2:</b> Sell if the holding period surpasses the maximum number of position days.</li>                
            </ul>
        </div>

        <div class="section">
            <h2>Optimization</h2>
            <p>Adjust and refine the strategy parameters to improve performance, but avoid overfitting to historical data, which can lead to poor future performance.</p>
            <div class="code">
                <p>BUY_THREAHOLD = -0.004</p>
                <p>SELL_TARGET = 0.05</p>
                <p>MAX_POSITION_DAY = 10</p>
            </div>            
        </div>

        <div class="section">
            <h2>Backtesting Result</h2>
            <p>Over the past 10 years, our simulation resulted in <b>104 trades</b>. These will be evaluated in the following section.</p>
            <img src="@/assets/images/trading/trade_spy_xyld.png">
            <p></p>
            <v-btn color="primary" @click="handleButtonClick">Learn More</v-btn>
        </div>
    </div>
</template>
  
<script>
export default {
  methods: {
    handleButtonClick() {
        this.$emit('change-tab', 'metrics');
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
  