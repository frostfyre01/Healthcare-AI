<template>
    <v-container>
      <div class="text-Left">
        <div class="text-body-4 font-weight-light mb-n1 page-title"><v-icon>mdi-finance</v-icon>&nbsp;Data Analysis</div>
        <h2 class="text-h4 font-weight-black">Data-Driven Analysis of Stock Trading Strategies</h2>
        <hr/>
        <br/>
      </div>
  
      <v-tabs
        v-model="tab"
        align-tabs="left"
        color="deep-purple-accent-4"
      >
        <v-tab value="overview">Overview</v-tab>
        <v-tab value="mystrategy">My Strategy</v-tab>
        <v-tab value="implement">Implementation</v-tab>
        <v-tab value="metrics">Performance Metrics</v-tab>
        <v-tab value="competition">Competition</v-tab>      
      </v-tabs>
  
      <v-card-text>
        <v-tabs-window v-model="tab">
          <v-tabs-window-item value="overview">
            <trading_overview @change-tab="handleTabChange"/>
          </v-tabs-window-item>
  
          <v-tabs-window-item value="mystrategy">
            <trading_mystrategy @change-tab="handleTabChange"/>
          </v-tabs-window-item>

          <v-tabs-window-item value="implement">
            <trading_implement @change-tab="handleTabChange"/>
          </v-tabs-window-item>

          <v-tabs-window-item value="metrics">
            <trading_metrics @change-tab="handleTabChange"/>
          </v-tabs-window-item>
  
          <v-tabs-window-item value="competition">
            <trading_competition/>
          </v-tabs-window-item>
        </v-tabs-window>
      </v-card-text>
    </v-container>
  </template>
  
  <script>
  import trading_overview from '../components/trading/trading-overview.vue'
  import trading_mystrategy from '../components/trading/trading-mystrategy.vue'
  import trading_implement from '../components/trading/trading-implement.vue'
  import trading_metrics from '../components/trading/trading-metrics.vue'
  import trading_competition from '../components/trading/trading-competition.vue'

  export default {
    components: {
      trading_overview,
      trading_implement,
      trading_mystrategy,
      trading_metrics,
      trading_competition,
    },
    data: () => ({
        tab: null,
    }),
    methods: {
      handleTabChange(newTab) {
        this.tab = newTab;
    }

  }
  }
  </script>
  
  <style scoped>
    ul {
      list-style-type: disc;
      margin-left: 20px;
    }
    .page-title {
      color: blueviolet;
    }
  </style>
  