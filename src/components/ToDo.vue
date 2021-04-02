<template>
  <div class="shadow pl-lg-3 py-2 mb-1 bg-white ">
    <div class="input-group w-auto align-items-center">

<!--        <div v-bind:class="{'done': todo.done }">-->
          <input type="checkbox" :checked=todo.done @change="todo.done = !todo.done">

          <label class="pl-2" v-on:click="markfinished">{{ todo.description }}</label>
<!--        </div>-->

        <button type="button" class="btn btn-light" style="position: absolute; right: 0;" v-on:click="deleteTodo(todo)">&times;</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ToDo',
  props: [
    "todo"
  ],
  methods: {
    markfinished() {
      this.todo.done = !this.todo.done
    },
    deleteTodo(todo) {
      this.$emit('delete-todo', todo);
    },
  }
}
</script>

<style scoped>

  .strikethrough:checked + label{
    text-decoration:line-through;
  }
</style>