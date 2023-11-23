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
      const response = await $axios.get('/api/tasks'); 
    this.tasks = response.data;
  }
};
</script>
