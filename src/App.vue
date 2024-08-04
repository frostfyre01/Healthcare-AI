<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" width="256">
      <v-list nav>
        <v-list-item prepend-icon="mdi-home" title="Home" link to="/"></v-list-item>
        <v-list-item prepend-icon="mdi-home" title="MiRNA" link to="/mirna"></v-list-item>
        <!-- Add more items as needed -->
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <router-view />
    </v-main>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <v-toolbar-title>My Application</v-toolbar-title>
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

<style>
/* Add any custom styles for your layout here */
</style>
