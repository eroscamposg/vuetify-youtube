<template>
  <v-container class="home">
    <v-row>
      <!-- en dispositivos pequeños, utiliza solo 6 columnas XS6-->
      <v-col class="red darken-1" cols="12">
        <h1>12</h1>
      </v-col>
      <v-col class="deep-purple lighten-3" cols="6">
        <h1>6</h1>
      </v-col>
      <v-col class="blue lighten-3" cols="6">
        <h1>6</h1>
      </v-col>
    </v-row>
    <v-row class="mt-5 secondary" justify="center" align="center" style="height:300px">
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

    <v-row>
      <v-col xs="12" sm="6">
        <v-card>
          <v-img src="https://cdn.vuetifyjs.com/images/cards/store.jpg">
            <v-container fill-height justify="center">
              <v-row>
                <v-col align="center">
                  <h3 class="headline white--text">Lorem, ipsum dolor.</h3>
                </v-col>
              </v-row>
            </v-container>
          </v-img>
          <v-card-title>
            <h2>Lorem, ipsum dolor.</h2>
          </v-card-title>
          <v-card-text>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Excepturi dignissimos vitae minima? Eveniet quas veritatis consequuntur asperiores tempora quis cumque nobis sint voluptatem similique eligendi cum, eius, debitis quidem non.</p>
          </v-card-text>
          <v-card-actions>
            <v-btn color="info" flat="true">Acción</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
      <v-col xs="12" sm="6">
        <v-card>
          <v-img src="https://cdn.vuetifyjs.com/images/cards/store.jpg"></v-img>
          <v-card-title>
            <h2>Lorem, ipsum dolor.</h2>
          </v-card-title>
          <v-card-text>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Excepturi dignissimos vitae minima? Eveniet quas veritatis consequuntur asperiores tempora quis cumque nobis sint voluptatem similique eligendi cum, eius, debitis quidem non.</p>
          </v-card-text>
          <v-card-actions>
            <v-btn color="info" flat="true" @click="dialog = true ">Acción</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>

    <!-- DIALOG. Persistent, solo haciendole click al boton pueden salir del dialog-->
    <v-dialog
      v-model="dialog"
      scrollable
      persistent
      :overlay="false"
      max-width="500px"
      transition="dialog-transition"
    >
      <v-card>
        <v-card-title primary-title>Title</v-card-title>
        <v-card-text>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cumque explicabo modi perferendis numquam. Suscipit, ab minima? Praesentium iusto saepe sed quo, minus facilis iure earum odio ad quaerat aut similique!</v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn color="success" @click="dialog = false">Accion</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home",
  components: {},
  data() {
    return {
      dialog: true
    };
  }
};
</script>

<style scoped>
h1 {
  justify-content: center;
}
</style>
