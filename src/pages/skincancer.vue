<template>
  <v-container>
    <div class="text-Left">
      <div class="text-body-4 font-weight-light mb-n1 page-title"><v-icon>mdi-pill</v-icon>&nbsp;Image Classification</div>
      <h2 class="text-h4 font-weight-black">Skin cancer detection</h2>
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
          <ImageUpload imagetype="sc"/>
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
        { name: 'sample_1.jpg', url: 'sample_pics/skincancer/sample_1.jpg' },
        { name: 'sample_2.jpg', url: 'sample_pics/skincancer/sample_2.jpg' },
        { name: 'sample_3.jpg', url: 'sample_pics/skincancer/sample_3.jpg' },
        { name: 'sample_4.jpg', url: 'sample_pics/skincancer/sample_4.jpg' },
        { name: 'sample_5.jpg', url: 'sample_pics/skincancer/sample_5.jpg' },
        { name: 'sample_6.jpg', url: 'sample_pics/skincancer/sample_6.jpg' },
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
