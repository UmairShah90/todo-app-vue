<template>
  <Header heading="TodoList"/>
  <AddTodo v-on:add-todo="addTodo" />
  <Todos :todos="todos" v-on:del-todo="deleteTodo" />
</template>

<script>
import Todos from "./components/Todos.vue";
  import Header from './components/layout/Header.vue'
  import AddTodo from './components/AddTodo.vue'
  import axios from 'axios'
export default {
  name: "App",
  components: {
    Todos,
    Header,
    AddTodo
  },

  data() {
    return {
      todos: [],
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(newTodo){
    this.todos = [...this.todos,newTodo]
  },
  },
  created(){
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
    .then(res => this.todos =  res.data)
    .catch(err => console.log(err))
  }
  
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
 .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }
</style>
