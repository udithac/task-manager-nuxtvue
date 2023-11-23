<template>
  <div>
    <h1>Task Manager Overview</h1>
    <TaskList :tasks="tasks" @delete-task="handleDeleteTask" />
    <TaskForm @submit="createTask" />
    <h4><hr>Note: There is no Database linked!, The Page Refresh will clear the Form!!!</h4>
  </div>
</template>

<script>
import TaskList from '~/components/TaskList.vue';
import TaskForm from '~/components/TaskForm.vue';

export default {
  components: {
    TaskList,
    TaskForm
  },
  data() {
    return {
      tasks: []
    };
  },
  methods: {
    handleDeleteTask(taskId) {
      const index = this.tasks.findIndex(t => t.id === taskId);
      if (index !== -1) {
        this.tasks.splice(index, 1);
      }
    },
    createTask(newTask) {
      // Update the tasks array with the new task
      this.tasks.push(newTask);
    }
  },
  async fetch({ $axios }) {
    try {
      this.tasks = [
        { id: 1, name: 'Task 1', dueDate: '2023-12-01', completed: false },
        { id: 2, name: 'Task 2', dueDate: '2023-12-05', completed: true },
      ];
    } catch (error) {
      console.error('Error fetching tasks:', error);
      this.tasks = [];
    }
  }
};
</script>

<style>
  /* Add your component-specific styles here */
</style>
