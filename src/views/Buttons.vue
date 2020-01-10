<template>
  <v-container>
    <v-row>
      <v-col>
        <v-btn>Texto</v-btn>
        <v-btn color="primary">Texto</v-btn>
        <v-btn color="secondary">Texto</v-btn>

        <v-btn color="secondary" text>Sin Fondo</v-btn>
        <v-btn color="warning" large>text</v-btn>
        <v-btn color="warning" small>text</v-btn>

        <v-btn color="warning" large :disabled="true">Disabled</v-btn>

        <!--Depressed no tiene sombra -->
        <v-btn color="info" depressed>Depressed</v-btn>

        <!-- WITH ICONS -->
        <v-btn>
          <v-icon>forum</v-icon>
        </v-btn>

        <v-btn color="primary" icon flat>
          <v-icon>forum</v-icon>
        </v-btn>

        <v-btn color="primary" fab>
          <v-icon>forum</v-icon>
        </v-btn>

        <v-btn color="primary" fab small>
          <v-icon>forum</v-icon>
        </v-btn>

        <v-btn color="primary" fab large>
          <v-icon>forum</v-icon>
        </v-btn>

        <v-btn color="primary">
          Texto
          <v-icon>forum</v-icon>
        </v-btn>

        <v-btn color="primary">
          Texto
          <v-icon class="ml-2">forum</v-icon>
        </v-btn>

        <v-btn color="primary">
          Texto
          <v-icon right>forum</v-icon>
        </v-btn>

        <v-btn color="success" outlined="true">
          Texto
          <v-icon right>forum</v-icon>
        </v-btn>

        <v-btn color="success" outlined="true" block>
          Texto
          <v-icon right>forum</v-icon>
        </v-btn>

        <v-btn color="primary" rounded="true">Rounded</v-btn>
        <!-- TEXT for no bakcground color-->
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>