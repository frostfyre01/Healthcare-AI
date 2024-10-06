<template>
   <div class="container">
        <v-alert type="info" border="left" prominent>
            Please use the following link to access the Jupyter Notebook:
            <v-btn text @click="openLink" class="ml-2">Open Notebook</v-btn>
        </v-alert>
        <div class="section">
            <h2>Data Splitting</h2>
            <p>Divide the dataset into training, validation, and test sets.</p>
            <img src="@/assets/images/miRNA/data_split_diagram.png">
            <p>separates the shuffled data into training (20%) and test (80%) sets.</p>
        </div>

        <div class="section">
            <h2>Model Training</h2>
            <div class="code">
                <p>feature_list = [feature1, feature2]</p>
                <p>X = train_data.loc[:, train_data.columns.isin(feature_list)]</p>
                <p>y = train_data['class']</p>
                <p>X_train, X_val, y_train, y_val = train_test_split(X, y, random_state=1)</p>
                <p>model = xgb.XGBClassifier()</p>
                <p>model.fit(X_train, y_train)</p>
                <p>model.save_model(s_no + '.xgb')</p>
            </div> 

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
        this.$emit('change-tab', 'metrics');
    },
    openLink() {
      window.open('https://deepnote.com/app/healthcare-ai-web/miRNA-cancer-detection-8bcf6c22-7a5a-48dc-85d6-e976abbf3aaa', '_blank');
    },
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
  