<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <Header />
    <AddTodo />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
    
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";
import Header from "./components/layout/header"

export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddTodo
  },
  data() 
  {
    return {
      todos: [
        {
          id: 1,
          title: "To-do One",
          completed: false
        },
        {
          id: 2,
          title: "To-do Two",
          completed: false
        },
        {
          id: 3,
          title: "To-do Three",
          completed: false
        }
      ]
    }
  },
  methods:
  {
    deleteTodo(id)
    {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
