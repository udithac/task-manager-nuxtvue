<template>
  <div>
    <h1>Task Details</h1>
    <div v-if="task">
      <p><strong>Name:</strong> {{ task.name }}</p>
      <p><strong>Due Date:</strong> {{ task.dueDate }}</p>
      <p><strong>Status:</strong> {{ task.completed ? 'Completed' : 'Incomplete' }}</p>
      <!-- Add other task details as needed -->
    </div>
    <div v-else>
      <p>No task selected</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    taskId: Number,
    tasks: Array,
  },
  computed: {
    task() {
      return this.tasks.find(task => task.id === this.taskId);
    },
  },
};
</script>

<style>
/* Add your component-specific styles here */
</style>
