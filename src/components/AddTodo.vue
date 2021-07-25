<template>
  <form @submit.prevent="addTodo">
    <input type="text" name="title" v-model="title" placeholder="Add Todo..." />
    <input type="submit" value="Submit" class="btn" />
  </form>
</template>

<script>
export default {
    name: 'AddTodo',
    data(){
        return{
            title: ''
        }
    },
    methods: {
      addTodo() {
          const newTodo = {
             title: this.title,
             completed: false
          }
          this.$emit('add-todo',newTodo)
          this.title = ''
      }
    }
};
</script>

<style scoped>
form {
  margin: 10px;
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 8px;
  border-top-left-radius: 5px;
  border-bottom-left-radius: 5px;
}
input[type="submit"] {
  flex: 2;
  border-top-right-radius: 5px;
  border-bottom-right-radius: 5px;

}
</style>
