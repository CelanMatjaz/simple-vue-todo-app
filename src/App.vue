<template>
  <div id="root">
    <AddTodo :addTodo="addTodo" />
    <Todos :todos="todos" :removeTodo="removeTodo" />
  </div>
</template>

<script>
import AddTodo from "./components/AddTodo";
import Todos from "./components/Todos";

export default {
  name: "App",
  components: {
    AddTodo,
    Todos,
  },
  methods: {
    removeTodo(index) {
      this.$data.todos.splice(index, 1);
    },
    addTodo(text) {
      this.$data.todos.push(text);
    },
  },
  data() {
    return {
      todos: [],
    };
  },
};
</script>

<style>
body {
  padding: 0;
  margin: 0;
  width: 100vw;
  min-width: 500px;
  font-family: Arial, Helvetica, sans-serif;
}

* {
  box-sizing: border-box;
}

#root {
  margin: 20px auto 0;
  width: 500px;
  padding: 40px 40px 20px;
  background-color: #646464;
}
</style>
