<template>
  <v-dialog v-model="dialog" max-width="600px">
    <template v-slot:activator="{ on, attrs }">
      <v-btn color="primary" dark v-bind="attrs" v-on="on">
        Add Todos
      </v-btn>
    </template>
    <v-card>
      <v-card-title>
        <span class="text-h5">Add Todo</span>
      </v-card-title>
      <v-card-text>
        <v-container>
          <v-row>
            <v-text-field
              type="text"
              v-model="title"
              placeholder="Add Todo"
              :rules="nameRules"
              clearable
            ></v-text-field>
          </v-row>
        </v-container>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="blue darken-1" text @click="dialog = false">
          Close
        </v-btn>
        <v-btn color="blue darken-1" text @click="onSubmit">
          Add
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodo",
  data() {
    return {
      dialog: false,
      title: "",
      nameRules: [(v) => !!v || "Name is required"],
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(event) {
      event.preventDefault();
      if (this.title === "") {
        this.title !== this.title;

        alert("This fieldd can't be empty!!!");
      } else {
        this.addTodo(this.title);
      }

      this.title = "";
    },
  },
};
</script>

<style scoped></style>
