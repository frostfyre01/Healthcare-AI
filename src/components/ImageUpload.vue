<template>
    <v-file-input
      v-model="image"
      :accept="imagetype"
      @change="handleImageUpload"
      outlined
      clearable
    />
    <!-- Image Preview -->
    <v-img
      v-if="imagePreview"
      :src="imagePreview"
      class="mt-4 image-preview"
      contain
      max-height="200"
      max-width="50%"
    />
    <!-- Classify Result -->
    <v-table v-if="items">
    <thead>
      <tr>
        <th class="text-left"></th>
        <th class="text-left">Name</th>
        <th class="text-left">Confidence</th>
      </tr>
    </thead>
    <tbody>
      <tr
        v-for="item in items"
        :key="item.name"
      >
        <td style="width: 10%" :class="{ 'highlight': item.isTopClass }"><v-icon icon="mdi-check-circle" v-if="item.isTopClass"></v-icon></td>
        <td :class="{ 'highlight': item.isTopClass }">{{ item.name }}</td>
        <td :class="{ 'highlight': item.isTopClass }">{{ item.confidence }}%</td>
      </tr>
    </tbody>
    </v-table>
    
    <!-- Button Row -->
    <v-card title="Upload Image" flat>
    <v-progress-linear
      v-if="isBusy"
      color="yellow-darken-2"
      indeterminate
    >
    </v-progress-linear>
    <v-row class="mt-4" align="center">
      <v-col cols="auto">
        <v-btn
          v-if="image"
          @click="submitImage"
          color="primary"
        >
          Submit
        </v-btn>
      </v-col>
      <v-col cols="auto">
        <v-btn
          v-if="imagePreview"
          @click="clearImage"
          color="red"
        >
          Clear
        </v-btn>
      </v-col>
    </v-row>
    </v-card>
  </template>
  
  <script>
  import SERVICE_CONFIG from '@/service_config'

  export default {
    props: {
      imagetype: {
        type: String,
        default: 'mpox' 
      }
    },
    data() {
      return {
        image: null, // Holds the selected image file
        imagePreview: null, // Holds the image preview URL
        items: null,
        isBusy: false,
      };
    },
    methods: {
      handleImageUpload() {
        if (this.image) {
          const fileType = this.image.type;
          if (fileType.startsWith('image/')) {
            const reader = new FileReader();
            reader.onload = e => {
              this.imagePreview = e.target.result;
              this.items = null;
            };
            reader.readAsDataURL(this.image);
          } else {
            this.$emit('error', 'Selected file is not an image.');
            this.image = null;
          }
        } else {
          this.imagePreview = null;
        }
      },
      clearImage() {
        this.image = null;
        this.imagePreview = null;
        this.items = null;
      },
      submitImage() {
        if (this.image) {
          const formData = new FormData();
          formData.append('file', this.image);
          formData.append('imagetype', this.imagetype);
          this.isBusy = true;
          fetch(SERVICE_CONFIG.CLASSIFY_URL, {
            method: 'POST',
            body: formData
          })
          .then(response => response.json())
          .then(data => {
            this.isBusy = false;
            this.setResult(data.AllClasses, data.TopClass);
            console.log('Success:', data);
          })
          .catch(error => {
            console.error('Error:', error);
          });
        }
      },
      setResult(data, topClass) {
        this.items = [];
        data.forEach((item) => {
          var name = item.Name.Name;
          var confidence = (item.Confidence * 100).toFixed(1);
          var isTopClass = (item.Name.Id == topClass.Name.Id);
          this.items.push({name: name, confidence: confidence, isTopClass: isTopClass})
        });

      }
    }
  };
  </script>
  
  <style scoped>
    .v-file-input {
      max-width: 400px;
    }
    .v-btn {
      margin-top: 1rem;
    }
    .image-preview {
        align-self: flex-start; /* Align the image to the left */
        margin-top: 1rem; /* Space above the image */
    }
    .v-row {
    margin-bottom: 1rem; /* Space below the button row */
    }
    .highlight {
      background-color: yellowgreen;
    }
  </style>
  