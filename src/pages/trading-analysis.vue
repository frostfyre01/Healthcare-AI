<template>
    <v-container>
      <div class="text-Left">
        <div class="text-body-4 font-weight-light mb-n1 page-title"><v-icon>mdi-zodiac-cancer</v-icon>&nbsp;Data Analysis</div>
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
        <v-tab value="basics">Basics</v-tab>
        <v-tab value="mystrategy">My Strategy</v-tab>
        <v-tab value="metrics">Metrics</v-tab>
        <v-tab value="application">Application</v-tab>      
      </v-tabs>
  
      <v-card-text>
        <v-tabs-window v-model="tab">
          <v-tabs-window-item value="overview">
            <trading_overview @change-tab="handleTabChange"/>
          </v-tabs-window-item>
  
          <v-tabs-window-item value="basics">
            <trading_basics @change-tab="handleTabChange"/>
          </v-tabs-window-item>
  
          <v-tabs-window-item value="mystrategy">
            <trading_mystrategy @change-tab="handleTabChange"/>
          </v-tabs-window-item>
  
          <v-tabs-window-item value="metrics">
            <trading_metrics @change-tab="handleTabChange"/>
          </v-tabs-window-item>
  
          <v-tabs-window-item value="application">
          </v-tabs-window-item>
        </v-tabs-window>
      </v-card-text>
    </v-container>
  </template>
  
  <script>
  import trading_overview from '../components/trading/trading-overview.vue'
  import trading_basics from '../components/trading/trading-basics.vue'
  import trading_mystrategy from '../components/trading/trading-mystrategy.vue'
  import trading_metrics from '../components/trading/trading-metrics.vue'

  export default {
    components: {
      trading_overview,
      trading_basics,
      trading_mystrategy,
      trading_metrics,
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
  