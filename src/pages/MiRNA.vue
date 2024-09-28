<template>
  <v-container>
    <div class="text-Left">
      <div class="text-body-4 font-weight-light mb-n1 page-title"><v-icon>mdi-dna</v-icon>&nbsp;miRNA</div>
      <h2 class="text-h4 font-weight-black">miRNA Biomarkers: A Path to Earlier Cancer Diagnosis</h2>
      <hr/>
      <br/>
    </div>

    <v-tabs
      v-model="tab"
      align-tabs="left"
      color="deep-purple-accent-4"
    >
      <v-tab value="overview">Overview</v-tab>
      <v-tab value="data">Data</v-tab>
      <v-tab value="model">Model</v-tab>
      <v-tab value="metrics">Metrics</v-tab>
      <v-tab value="application">Application</v-tab>      
    </v-tabs>

    <v-card-text>
      <v-tabs-window v-model="tab">
        <v-tabs-window-item value="overview">
          <miRNA_overview @change-tab="handleTabChange"/>
        </v-tabs-window-item>

        <v-tabs-window-item value="data">
          data
        </v-tabs-window-item>

        <v-tabs-window-item value="model">
          model
        </v-tabs-window-item>

        <v-tabs-window-item value="metrics">
          metrics
        </v-tabs-window-item>

        <v-tabs-window-item value="application">
            <miRNA_Input/>
        </v-tabs-window-item>
      </v-tabs-window>
    </v-card-text>
  </v-container>
</template>

<script>
import miRNA_Input from '../components/miRNA_Input.vue';
import miRNA_overview from '../components/miRNA/miRNA-overview.vue'

export default {
  components: {
    miRNA_Input,
    miRNA_overview
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
