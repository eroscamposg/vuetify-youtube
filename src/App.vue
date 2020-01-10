<template>
  <v-app>
    <!-- v-app-bar reemplaza a v-toolbar -->
    <v-app-bar app="true">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <!-- NAVIGATION DRAWERS -->

      <v-toolbar-title>Lol</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn class="success">Ingreso</v-btn>
      <v-btn class="warning ml-5">Error</v-btn>
    </v-app-bar>

    <v-navigation-drawer app="true" v-model="drawer" temporary="true" dark>
      <v-row class="mt-4">
        <v-col justify="center" align="center">
          <v-avatar>
            <img src="https://randomuser.me/api/portraits/men/81.jpg" />
          </v-avatar>
        </v-col>
      </v-row>
      <v-row>
        <v-col justify="center" align="center">
          <p class="white--text headline">Juanito Perez</p>
        </v-col>
      </v-row>
    </v-navigation-drawer>
    <v-content>
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: "App",
  components: {},

  data() {
    return {
      drawer: true
    };
  }
};
</script>
