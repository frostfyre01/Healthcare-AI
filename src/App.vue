<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" width="256">
      <v-list nav>
        <v-list-item prepend-icon="mdi-home" title="Home" link to="/"></v-list-item>
        <v-list-item prepend-icon="mdi-dna" title="miRNA" link to="/mirna"></v-list-item>
        <v-list-item prepend-icon="mdi-pill" title="Skin Cancer Detection" link to="/skincancer"></v-list-item>
        <v-list-item prepend-icon="mdi-virus-outline" title="MPOX Detection" link to="/mpox"></v-list-item>
        <v-list-item prepend-icon="mdi-finance" title="Stock Trading Analysis" link to="/trading-analysis"></v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <router-view />
    </v-main>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <a href="/" class="v-btn v-btn--text v-btn--router ma-0 pa-0">
        My Application
      </a>
      <v-spacer />
    </v-app-bar>

    <!-- Footer -->
    <AppFooter />
  </v-app>
</template>

<script>
import AppFooter from './components/AppFooter.vue';

export default {
  components: {
    AppFooter,
  },
  data: () => ({
    drawer: false
  })
}
</script>

<style scoped>
/* Custom styles for drawer item hover effect */
.v-list-item:hover {
  background-color: #2872a7; /* Light blue color */
}
</style>
