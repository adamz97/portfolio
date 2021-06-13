<template v-for="todo in todos" :key="todo.id">
  <v-data-table
    :headers="headers"
    :items="allTodos"
    :items-per-page="5"
    class="elevation-5"
  >
    <template v-slot:[`item.actions`]="{ id }">
      <v-icon @click="deleteTodo(id)" medium> mdi-pencil </v-icon>

      <v-icon @click="deleteTodo(id)" medium> mdi-delete </v-icon>
    </template>
  </v-data-table>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
  data() {
    return {
      headers: [
        { text: "ID", value: "id", sortable: true },
        { text: "Title", value: "title" },
        { text: "Edytuj/Usuń", value: "actions", sortable: false },
      ],
    };
  },

  methods: {
    ...mapActions(["fetchTodos", "deleteTodo"]),
  },

  computed: mapGetters(["allTodos"]),

  created() {
    this.fetchTodos();
  },
};
</script>
<style scoped></style>
