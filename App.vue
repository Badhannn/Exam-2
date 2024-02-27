<template>
  <div class="app">
    <ul>
      <li v-for="(task, index) in tasks" :key="index">
        {{ task.name }} - {{ task.time }}
        <button @click="editTask(index)">Edit</button>
      </li>
    </ul>
    <EditForm v-if="showEditForm" @submit="updateTask" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import EditForm from './components/EditForm.vue';

const tasks = ref([
  { name: 'Task 1', time: 30 },
  { name: 'Task 2', time: 40 },
  { name: 'Task 3', time: 60 },
  { name: 'Task 4', time: 45 },
  { name: 'Task 5', time: 50 },
]);

const showEditForm = ref(false);
let editingIndex = null;

const editTask = (index) => {
  showEditForm.value = true;
  editingIndex = index;
};

const updateTask = (updatedTask) => {
  tasks.value[editingIndex] = updatedTask;
  showEditForm.value = false;
};
</script>
