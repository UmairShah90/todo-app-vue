<template>
  <div class="todo-item" :class="{ 'is-complete': todo.completed }">
    <p>
      <input type="checkbox" @change="markComplete" />
      {{ todo.title }}
      <button @click="$emit('del-todo',todo.id)" class="del">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: {
    todo: Object,
  },
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.todo-item {
  margin: 15px;
  border-radius: 5px;
  box-shadow: 1px 1px 5px grey;  
  background: #f4f4f4;
  border-bottom: 1px solid #ccc;
   border-left: 5px solid red;
  padding: 10px;
}
input[type="checkbox"]{
    background: red;
} 
.is-complete {
  text-decoration: line-through;
}
.del {
  background: red;
  border-radius: 50%;
  padding: 5px 10px;
  position: relative;
  bottom: 3px;
  border: none;
  cursor: pointer;
  color: white;
  float: right;
}
</style>
