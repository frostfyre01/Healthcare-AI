<template>
  <div>
    <v-table class="file-table">
      <thead>
        <tr>
          <th class="text-left">Sample Images</th>
        </tr>
      </thead>
      <tbody>
        <tr v-if="!files.length">
          <td>No files available.</td>
        </tr>
        <tr v-for="item in files" :key="item.name" class="table-row">
          <span>{{ item.name }}</span>
           <a @click.prevent="downloadSampleFile(item.url)">
              <v-icon icon="mdi-download-box" class="download-icon"></v-icon>
           </a>
        </tr>
      </tbody>
    </v-table>
  </div>
</template>

<script>
export default {
  props: {
    files: {
      type: Array,
      required: true,
    },
  },
  methods: {
    downloadSampleFile(fileName) {
      const link = document.createElement('a');
      link.href = '/downloads/' + fileName;;
      link.download = ''; // Use the filename from the URL
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    },   
  },
};
</script>

<style>
.file-table {
  min-width: 100px; 
  max-width: 300px; 
  width: 100%; 
  overflow: auto;  
}
.table-row {
  height: 40px; /* Set your desired row height */
}
.download-icon {
  margin-left: 8px; /* Space between name and icon */
  color: #007bff; /* Optional: color for the icon */
  text-decoration: none; /* Remove underline */
  cursor: pointer; /* Change cursor to pointer */
}
</style>
