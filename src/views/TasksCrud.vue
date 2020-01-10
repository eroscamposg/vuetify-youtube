<template>
  <v-container>
    <v-row>
      <v-col md="6">
        <v-card class="mb-3" v-for="(task, index) in taskList" :key="index">
          <v-card-title primary-title>
            <v-chip color="pink" label text-color="white">
              <v-icon left>label</v-icon>
              {{task.title}}
            </v-chip>
          </v-card-title>
          <v-card-text>
            <p>{{task.desc}}</p>
          </v-card-text>
          <div align="center">
            <v-btn color="warning" @click="edit(index)">Editar</v-btn>
            <v-btn class="ma-5" color="error" @click="deleteTask(task.id)">Eliminar</v-btn>
          </div>
        </v-card>

        <!-- <v-card class="mb-3">
          <v-card-title primary-title>
            <v-chip color="pink" label text-color="white">
              <v-icon left>label</v-icon>Titulo de Tarea #2
            </v-chip>
          </v-card-title>
          <v-card-text>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Et suscipit nulla cupiditate neque minima dolore eum accusamus adipisci. Qui temporibus porro iusto impedit! Cum modi praesentium error commodi illo distinctio!</p>
          </v-card-text>
          <div align="center">
            <v-btn color="warning">Editar</v-btn>
            <v-btn class="ma-5" color="error">Eliminar</v-btn>
          </div>
        </v-card>-->
      </v-col>
      <v-col md="6" v-if="formAddNew">
        <v-card class="mb-3 pa-3">
          <v-form @submit.prevent="addTask">
            <v-text-field name="title" label="Titulo de la tarea" id="id" v-model="title"></v-text-field>
            <v-textarea label="Descripción de la tarea" v-model="description"></v-textarea>
            <v-btn block color="success" type="submit">Agregar Tarea</v-btn>
          </v-form>
        </v-card>
      </v-col>

      <v-col md="6" v-if="!formAddNew">
        <v-card class="mb-3 pa-3">
          <v-form @submit.prevent="editTask">
            <v-text-field name="title" label="Titulo de la tarea" id="id" v-model="title"></v-text-field>
            <v-textarea label="Descripción de la tarea" v-model="description"></v-textarea>
            <v-btn block color="warning" type="submit">Editar Tarea</v-btn>
          </v-form>
        </v-card>
      </v-col>
    </v-row>

    <!-- SNACKBAR -->
    <v-snackbar v-model="snackbar">
      {{ message }}
      <v-btn color="pink" text @click="snackbar = false">Cerrar</v-btn>
    </v-snackbar>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      taskList: [
        {
          id: 1,
          title: "Titulo de Tarea #1",
          desc:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Et suscipit nulla cupiditate neque minima dolore eum accusamus adipisci. Qui temporibus porro iusto impedit! Cum modi praesentium error commodi illo distinctio!"
        },
        {
          id: 2,
          title: "Titulo de Tarea #2",
          desc:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Et suscipit nulla cupiditate neque minima dolore eum accusamus adipisci. Qui temporibus porro iusto impedit! Cum modi praesentium error commodi illo distinctio!"
        }
      ],
      title: "",
      description: "",
      snackbar: false,
      message: "",
      formAddNew: true,
      indexTask: ""
    };
  },
  methods: {
    addTask() {
      console.log(this.title, this.description);
      if (this.title === "" || this.description === "") {
        this.snackbar = true;
        this.message = "Llena todos los campos!";
      } else {
        this.taskList.push({
          id: Date.now(),
          title: this.title,
          desc: this.description
        });

        this.title = "";
        this.description = "";

        this.message = "Tarea agregada!";
        this.snackbar = true;
      }
    },
    deleteTask(id) {
      //Retorna todos los task que tenga un ID diferente al que se pasas
      this.taskList = this.taskList.filter(e => e.id != id);
    },
    edit(index) {
      this.formAddNew = false;
      this.title = this.taskList[index].title;
      this.description = this.taskList[index].desc;
      this.indexTask = index;
    },
    editTask() {
      this.taskList[this.indexTask].title = this.title;
      this.taskList[this.indexTask].desc = this.description;

      this.title = "";
      this.description = "";

      this.message = "Editaste la tarea!";
      this.snackbar = true;

      this.formAddNew = true;
    }
  }
};
</script>