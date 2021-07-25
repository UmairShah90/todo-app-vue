<template>
  <div v-for="todo in todos" :key="todo.id">
    <TodoItem v-on:del-todo="$emit('del-todo',todo.id)" :todo="todo" />
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
  name: "Todos",
  components: {
    TodoItem,
  },
  props: {
    todos: Object,
  },
};
</script>

<style></style>
