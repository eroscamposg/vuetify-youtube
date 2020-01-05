<template>
  <v-container class="home">
    <v-row>
      <!-- en dispositivos pequeños, utiliza solo 6 columnas XS6-->
      <v-col
        class="red darken-1
"
        cols="12"
      >
        <h1>12</h1>
      </v-col>
      <v-col class="deep-purple lighten-3" cols="6">
        <h1>6</h1>
      </v-col>
      <v-col
        class="blue lighten-3
"
        cols="6"
      >
        <h1>6</h1>
      </v-col>
    </v-row>
    <v-row
      class="mt-5 secondary "
      justify="center"
      align="center"
      style="height:300px"
    >
      <v-col class="info d-flex justify-center" cols="3">
        <h1>Centrado</h1>
      </v-col>

      <v-col class="pink lighten-3 white--text d-flex justify-center" cols="3">
        <h1>Centrado</h1>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <h1 class="display-1 text-uppercase">Lorem, ipsum dolor.</h1>
        <h1 class="display-2 primary pa-5">Lorem, ipsum dolor.</h1>
        <h1 class="display-3 text-sm-center">Lorem, ipsum dolor.</h1>
        <h1 class="display-4">Lorem, ipsum dolor.</h1>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home",
  components: {}
};
</script>

<style scoped>
h1 {
  justify-content: center;
}
</style>
