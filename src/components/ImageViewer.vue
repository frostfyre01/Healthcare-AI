<template>
    <v-container>
      <!-- Thumbnail Image -->
      <v-img
        :src="thumbnailSrc"
        @click="showModal = true"
        class="thumbnail"
        :max-width="thumbnailMaxWidth"
      ></v-img>
  
      <!-- Modal for Larger Image -->
      <v-dialog v-model="showModal" :max-width="modalMaxWidth">
        <v-card>
          <v-img :src="largeImageSrc" class="large-image"></v-img>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn text @click="showModal = false">Close</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-container>
  </template>
  
  <script>
  export default {
    props: {
      thumbnailSrc: {
        type: String,
        required: true,
      },
      largeImageSrc: {
        type: String,
        required: true,
      },
      thumbnailMaxWidth: {
        type: [Number, String],
        default: 200,
      },
      modalMaxWidth: {
        type: [Number, String],
        default: '800px',
      },
      largeImageHeight: {
        type: [Number, String],
        default: 600,
      },
    },
    data() {
      return {
        showModal: false,
      };
    },
  };
  </script>
  
  <style scoped>
  .thumbnail {
    cursor: pointer;
  }
  .large-image {
    height: var(--large-image-height, 600px); /* Default height if not provided */
  }
  </style>
  