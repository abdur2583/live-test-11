<script setup>
import { ref } from 'vue'
import { Modal } from 'usemodal-vue3';
let isVisible = ref(false);
const tasks = ref([{
name: 'Task 1',
time: 30
}, {
name: 'Task 2',
time: 40
}, {
name: 'Task 3',
time: 60
}, {
name: 'Task 4',
time: 45
}, {
name: 'Task 5',
time: 50
}]);
</script>

<template>
  <div class="container">
    <h1>Task One</h1>
  </div>
  <div class="task">
    <ul>
    <li v-for="task in tasks" :key="task.name">
      {{ task.name }} ({{ task.time }} minutes)
      <button @click="isVisible(true)">Edit</button>
    </li>
  </ul>
  <div v-if="showPopup">
    <Popup v-model:show="showPopup" @update-task="updateTask">
      <h2>Edit Task</h2>
      <form @submit.prevent="updateTask">
        <label for="name">Name:</label>
        <input type="text" id="name" v-model="editedTask.name" required />

        <label for="time">Time (minutes):</label>
        <input type="number" id="time" v-model="editedTask.name" min="0" required />

        <button type="submit">Save</button>
      </form>
    </Popup>
  </div>
  </div>
  <Modal v-model:visible="isVisible">
    <div>your content...</div>
</Modal>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
li{
  list-style-type: none;
}
</style>
