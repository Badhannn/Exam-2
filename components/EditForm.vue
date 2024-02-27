  <script setup>
  import { ref } from 'vue';
  
  const editedTask = ref({
    name: '',
    time: 0,
  });
  
  const submitEdit = () => {
    // Emit an event to notify the parent component about the edit
    emit('submit', editedTask.value);
  };
  </script>

<template>
    <div class="edit-form">
      <input type="text" v-model="editedTask.name" placeholder="Task Name" />
      <input type="number" v-model="editedTask.time" placeholder="Time" />
      <button @click="submitEdit">Submit</button>
    </div>
  </template>
  
  <script>


</script>
  