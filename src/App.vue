<template>
  <div id="app">
    <add-todo />
    <filter-todo />
    <todo-item />
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem.vue";
import AddTodo from "./components/AddTodo.vue";
import FilterTodo from "./components/FilterTodo";

export default {
  name: "app",
  components: {
    TodoItem,
    AddTodo,
    FilterTodo
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  width: 50%;
}
</style>
