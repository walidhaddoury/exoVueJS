<template>
  <div id="app">
    <Horloge />
    <hr />
    <TodoList />
  </div>
</template>

<script>
import Horloge from "./components/Horloge.vue";
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: {
    Horloge,
    TodoList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
hr {
  size: 2px;
  background-color: black;
}
</style>
