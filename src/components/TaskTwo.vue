<script setup>
import { ref } from 'vue'


</script>

<template>
  <div class="container">
    <h1>Task Two</h1>
  </div>
  <div class="task2">
    <form @submit.prevent="updateTask">
        <label for="name">Name:</label>
        <input type="text" id="name"  required />
        <br>
        <label for="time">Time (minutes):</label>
        <input type="number" id="time" min="0" required />
        <br>
        <button type="submit">Save</button>
    </form>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
input{
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
}
button{
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  background-color: rgb(34, 192, 113);
}
</style>
