<template>
    <v-card title="Upload Image" flat>
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

    <!-- Button Row -->
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
        imagePreview: null // Holds the image preview URL
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
      },
      submitImage() {
        if (this.image) {
          const formData = new FormData();
          formData.append('file', this.image);
          formData.append('imagetype', this.imagetype);
  
          fetch(SERVICE_CONFIG.CLASSIFY_URL, {
            method: 'POST',
            body: formData
          })
          .then(response => response.json())
          .then(data => {
            console.log('Success:', data);
          })
          .catch(error => {
            console.error('Error:', error);
          });
        }
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
  </style>
  