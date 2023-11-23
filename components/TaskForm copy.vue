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
      // Check if the input is not empty
      if (this.newTask.name && this.newTask.dueDate) {
        // Emit an event to the parent component with the new task data
        this.$emit('submit', this.newTask);

        // Clear the form after submitting
        this.newTask = { name: '', dueDate: '' };
      }
    }
  }
};
</script>

<style >
/* Add your component-specific styles here */
</style>
