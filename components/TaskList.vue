<template>
  <div>
    <label>Sort by:</label>
    <select v-model="sortOption">
      <option value="name">Name</option>
      <option value="dueDate">Due Date</option>
    </select>

    <label>Filter by status:</label>
    <select v-model="filterOption">
      <option value="all">All</option>
      <option value="completed">Completed</option>
      <option value="incomplete">Incomplete</option>
    </select>
    <br>
    <hr>
    <label>:: Registered Tasks ::</label>

    <!-- Check if there are tasks to display -->
    <table v-if="sortedAndFilteredTasks.length > 0">
      <thead>
        <tr>
          <th>Name</th>
          <th>Due Date</th>
          <th>Status</th>
          <th v-if="filterOption === 'incomplete'">Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="task in sortedAndFilteredTasks" :key="task.id">
          <td>
          
          {{ task.name }}  <!--   <a :href="'/' + task.id">{{ task.name }}</a> -->
          </td>
          <td>{{ task.dueDate }}</td>
          <td>{{ task.completed ? 'Completed' : 'Incomplete' }}</td>
          <td>
            <button v-if="!task.completed" @click="markAsCompleted(task)">Mark as Completed</button>
            <button v-if="filterOption !== 'completed'" @click="deleteTask(task)">Delete Task</button>
          </td>
        </tr>
      </tbody>
    </table>

    <!-- Display "No data available" if there are no tasks -->
    <p v-else>No data available</p>
  </div>
</template>

<script>
export default {
  props: {
    tasks: Array
  },
  data() {
    return {
      sortOption: 'name',
      filterOption: 'all'
    };
  },
  computed: {
    sortedAndFilteredTasks() {
      let sortedTasks = [...this.tasks];

      if (this.sortOption === 'name') {
        sortedTasks.sort((a, b) => {
          const nameA = String(a.name);
          const nameB = String(b.name);
          return nameA.localeCompare(nameB);
        });
      } else if (this.sortOption === 'dueDate') {
        sortedTasks.sort((a, b) => new Date(a.dueDate) - new Date(b.dueDate));
      }

      if (this.filterOption === 'completed') {
        sortedTasks = sortedTasks.filter(task => task.completed);
      } else if (this.filterOption === 'incomplete') {
        sortedTasks = sortedTasks.filter(task => !task.completed);
      }

      return sortedTasks;
    }
  },
  methods: {
    markAsCompleted(task) {
      this.$set(task, 'completed', true);
    },
    deleteTask(task) {
      this.$emit('delete-task', task.id);
    }
  }
};
</script>

<style scoped>
table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 10px;
}

th, td {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: left;
}

th {
  background-color: #f2f2f2;
}
</style>
