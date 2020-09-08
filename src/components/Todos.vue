<template>
  <ul>
    <li v-for="(todo, i) of todos" v-bind:key="i" @click="deleteTodo(i)">{{todo}}</li>
  </ul>
</template>

<script>
export default {
  props: {
    todos: Array,
    removeTodo: Function,
  },
  methods: {
    deleteTodo(index) {
      this.$props.removeTodo(index);
    },
  },
};
</script>

<style>
ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

li {
  padding: 6px;
  font-size: 1.2rem;
  color: white;
  border: 1px solid white;
  border-radius: 3px;
  margin-top: 10px;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}

li:hover {
  text-decoration: line-through;
  cursor: pointer;
}
</style>