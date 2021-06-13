<template>
  <v-app id="inspire">
    <v-app-bar app prominent color="#primary" dark src="todo.jpg">
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
        ></v-img>
      </template>

      <v-app-bar-title default class="pa-8">Simple Todo</v-app-bar-title>
    </v-app-bar>
    <v-main class="grey lighten-3">
      <v-col class="text-right">
        <v-sheet min-height="70vh" rounded="lg" class=" pa-3">
          <add-todo></add-todo>
          <todo-table></todo-table>
        </v-sheet>
      </v-col>
    </v-main>
  </v-app>
</template>

<script>
import AddTodo from "./components/AddTodo.vue";
import TodoTable from "./components/TodoTable.vue";

export default {
  name: "App",

  components: {
    AddTodo,
    TodoTable,
  },
};
</script>
