<template>
  <div>
    <TaskDetail :taskId="id" :tasks="tasks" />
  </div>
</template>

<script>
import TaskDetail from '~/components/TaskDetail.vue';

export default {
  components: {
    TaskDetail
  },
  props: ['id'],
  async fetch({ $axios, params }) {
    // Fetch the list of tasks
    const response = await $axios.get('/api/tasks'); // Replace with your actual API endpoint
    this.tasks = response.data;
  }
};
</script>
