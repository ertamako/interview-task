<template>
  <div>
  <form @submit="addTodo">

    <input class="form-control shadow p-3 mb-5 bg-white rounded" type="text" v-model="description" name="description" placeholder="Write your task here">
    <div class="text-center">
    <button type="submit" class="btn btn-success btn-round">Add Task</button>
    </div>
  </form>
  </div>
</template>

<script>

export default {
  name: "AddTodo.vue",
  data() {
    return {
      description: ''
    }
  },
  methods:{
    addTodo(e){
      e.preventDefault();

      const newTask = {
        description: this.description,
        done: false
      }

      this.$emit('add-todo', newTask);
      this.description = '';
    }
  }
}
</script>

<style scoped>

</style>