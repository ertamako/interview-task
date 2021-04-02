<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col"></div>
        <div class="col-4">
          <br>
          <div class="text-center">
          <h1 class="text-secondary">TO-DO List</h1>
          </div>
<!--          Render the AddTodo component-->
        <AddTodo v-on:add-todo="addTodo"/>
<!--          Render the Todos component-->
        <Todos v-bind:todos="todos"/>
        </div>
        <div class="col"></div>
      </div>
    </div>
  </div>
</template>

<script>

import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";

export default {
  name: 'app',
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          description: 'Learn about Kubernetis',
          done: false
        },
        {
          description: 'Docker Deployment',
          done: true
        },
      ]
    }
  },
  methods: {
    addTodo(newTask) {
      this.todos = [...this.todos, newTask]
    }
  }
}
</script>

<style>
/*#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/
</style>
