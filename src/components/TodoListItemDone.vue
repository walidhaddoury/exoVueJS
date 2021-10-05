<template>
  <div>
    <span>{{ display.task }}</span>
    <button @click="deleteTask">Supprimer</button>
    <button @click="display.isDone = !display.isDone">
      PAS FINI
    </button>
  </div>
</template>

<script>
export default {
  name: "TodoListItemDone",
  props: {
    display: Object,
  },
  methods: {
    deleteTask: function() {
      this.$emit("delete");
    },
  },
};
</script>

<style scoped>
span {
  text-decoration: line-through;
  margin-right: 15px;
}
button {
  margin-right: 15px;
}
</style>
