<template>
  <div>
    <hr><h2>Create New Task</h2>
    <form @submit.prevent="submitForm">
      <label for="taskName">Task Name:</label>
      <input v-model="newTask.name" type="text" id="taskName" required>

      <label for="dueDate">Due Date:</label>
      <input v-model="newTask.dueDate" type="date" id="dueDate" required>

      <button type="submit">Add Task</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: {
        name: '',
        dueDate: ''
      }
    };
  },
  methods: {
    submitForm() {      
      if (this.newTask.name && this.newTask.dueDate) {        
        this.$emit('submit', this.newTask)
        this.newTask = { name: '', dueDate: '' };
      }
    }
  }
};
</script>

<style >
/* my css styles come here .... */
</style>
