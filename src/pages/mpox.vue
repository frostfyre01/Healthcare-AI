<template>
  <v-container>
    <div class="text-Left">
      <div class="text-body-4 font-weight-light mb-n1 page-title"><v-icon>mdi-virus-outline</v-icon>&nbsp;Image Classification</div>
      <h2 class="text-h4 font-weight-black">MPOX detection</h2>
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
          overview
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
          <ImageUpload imagetype="mpox"/>
          <FileTable :files="sampleFiles" />
        </v-tabs-window-item>
      </v-tabs-window>
    </v-card-text>
  </v-container>
</template>

<script>
import ImageUpload from '../components/ImageUpload.vue';
import FileTable from '../components/FileTable.vue';

export default {
  components: {
    ImageUpload,
    FileTable
  },
  data: () => ({
      tab: null,
      sampleFiles: [
        { name: 'sample_15.png', url: 'sample_pics/mpox/sample_15.png' },
        { name: 'sample_16.png', url: 'sample_pics/mpox/sample_16.png' },
        { name: 'sample_35.jpg', url: 'sample_pics/mpox/sample_35.jpg' },
        { name: 'sample_49.png', url: 'sample_pics/mpox/sample_49.png' },
        { name: 'sample_50.png', url: 'sample_pics/mpox/sample_50.png' },
      ]
    }),
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
