<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" width="256">
      <v-list>
        <v-list-item link to="/">
          <v-list-item-icon>
            <v-icon>mdi-home</v-icon>
          </v-list-item-icon>
          <v-list-item-title>Home</v-list-item-title>
        </v-list-item>
        <v-list-item link to="/mirna">
          <v-list-item-icon>
            <v-icon>mdi-information</v-icon>
          </v-list-item-icon>
          <v-list-item-title>About</v-list-item-title>
        </v-list-item>
        <!-- Add more items as needed -->
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <!-- Main content here -->
      <router-view />
    </v-main>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <v-toolbar-title>My Application</v-toolbar-title>
      <v-spacer />
      <!-- Add additional actions or components here -->
    </v-app-bar>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: false
  })
}
</script>

<style>
/* Add any custom styles for your layout here */
</style>
