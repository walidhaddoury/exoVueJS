<template>
  <div>
    <div>
      <h1>Liste des taches</h1>
    </div>
    <div>
      <div>
        <input v-model="input" type="text" />
        <button @click="addTask(input)">Ajouter</button>
      </div>
      <div>
        <ul>
          <li v-for="(display, index) in todolist" :key="index">
            <TodoListItem
              v-if="!display.isDone"
              :display="display"
              :index="index"
              @delete="deleteTask(index)"
            />
            <TodoListItemDone
              v-else
              :display="display"
              :index="index"
              @delete="deleteTask(index)"
            />
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import TodoListItem from "./TodoListItem.vue";
import TodoListItemDone from "./TodoListItemDone.vue";

export default {
  name: "TodoList",
  components: {
    TodoListItem,
    TodoListItemDone,
  },
  data: function() {
    return {
      input: "",
      todolist: [],
    };
  },
  methods: {
    addTask: function(input) {
      this.todolist.push({
        task: input,
        isDone: false,
      });
    },
    deleteTask: function(index) {
      this.todolist.splice(index, 1);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin-bottom: 10px;
}
</style>
