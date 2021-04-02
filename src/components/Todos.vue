<!--“Todos” component is the container where all the todos should be displayed-->

<template>
  <div>
    <br>
    <h6 class="text-secondary">Not finished tasks</h6>
      <div v-for="todo in todos" v-show="!todo.done">
        <ToDo v-bind:todo="todo" />
      </div>
    <br>
    <h6 class="text-secondary">Finished tasks</h6>
    <div v-for="todo in todos" v-show="todo.done">
        <ToDo v-bind:todo="todo" />
    </div>
  </div>

</template>

<script>
import ToDo from './ToDo';
export default {
  name: 'Todos',
  components: {
    ToDo
  },
  props:[
      "todos"
  ],


}
</script>

<style scoped>
</style>