<template>
  <form @submit="handleSubmit">
    <label>
      <input type="text" v-model="newTodoText" autofocus />
    </label>
    <button>Add todo</button>
  </form>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return { newTodoText: "" };
  },
  methods: {
    handleSubmit(e) {
      e.preventDefault();
      this.$props.addTodo(this.$data.newTodoText);
      this.$data.newTodoText = "";
    },
  },
  props: {
    addTodo: Function,
  },
};
</script>

<style scoped>
form input {
  width: 100%;
  padding: 4px;
  font-size: 1.5rem;
}

form button {
  padding: 8px;
  margin-top: 10px;
  border: 1px solid white;
  border-radius: 4px;
  color: white;
  background-color: #646464;
  font-weight: 400;
}

form button:hover {
  padding: 8px;
  margin-top: 10px;
  border: 1px solid #646464;
  color: #646464;
  background-color: white;
}
</style>