<template>
  <div>
    <span>{{ display.task }}</span>
    <button @click="deleteTask">Supprimer</button>
    <button @click="display.isDone = !display.isDone">
      FINI
    </button>
  </div>
</template>

<script>
export default {
  name: "TodoListItem",
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
  margin-right: 15px;
}
button {
  margin-right: 15px;
}
</style>
