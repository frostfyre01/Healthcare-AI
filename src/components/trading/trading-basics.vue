<template>
   <div class="container">
        <div class="section">
            <h2>Basics</h2>
            <p>Welcome to our latest trading strategy presentation. Our approach combines advanced analytical techniques with a deep understanding of market trends to deliver superior results. In this document, we will walk you through the core principles of our strategy, its benefits, and how you can get started.</p>
        </div>

        <div class="section">
            <h2>How It Works</h2>
            <p>Our trading strategy is built on a multi-faceted approach that includes technical analysis, fundamental analysis, and market sentiment tracking. By integrating these elements, we ensure a comprehensive understanding of market conditions and make informed trading decisions.</p>
        </div>

        <div class="section">
            <h2>Benefits</h2>
            <p>Adopting our trading strategy offers numerous advantages:</p>
            <ul>
                <li>Increased Accuracy: Higher precision in trade predictions and decision-making.</li>
                <li>Time Efficiency: Automated processes save time and reduce manual effort.</li>
                <li>Consistent Results: A proven track record of successful trades and strategies.</li>
            </ul>
        </div>

        <div class="section">
            <h2>Get Started</h2>
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
</style>
  