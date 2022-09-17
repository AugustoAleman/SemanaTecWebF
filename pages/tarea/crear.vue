<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <h2>Crear tarea</h2>
        <v-form>
          <v-text-field
            name="name"
            v-model="newTarea.name"
            outline
            label="Nombre de la tarea"
            id="id"
          ></v-text-field>      
        </v-form>
        <v-btn
          @click="saveTarea()"
          :loading="saving"
          rounded
          color="primary"
          :disabled="saved"
          >Crear</v-btn
        >
      </v-col>
    </v-row>
    <v-snackbar
      :timeout="-1"
      :value="true"
      absolute
      v-model="saved"
      bottom
      color="success"
      outlined
      right
    >
      Tu tarea ha sido asignada satisfactoriamente
      <template v-slot:action="{ attrs }">
        <v-btn color="pink" text v-bind="attrs" @click="saved = false">
          Cerrar
        </v-btn>
      </template>
    </v-snackbar>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      saving: false,
      saved: false,
      newTarea: {},
      date:null,
      time:null,
    };
  },
  methods: {
    saveTarea() {
      this.saving = true;
      this.$axios
        .$post("https://semanatecweb.herokuapp.com/assignment/create", this.newTarea)
        .then((response) => {
          console.log(response);
          this.saved = true;
          this.saving = false;
        });
    },
  },
};
</script>
