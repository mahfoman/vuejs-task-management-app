
<template>

  <header class="bg-gray-600 text-white p-4">
    <nav class="max-w-5xl mx-auto flex justify-between">
      <a href="#" class="text-lg font-semibold">Task Manager App</a>
    </nav>
  </header>

  <main class="flex-grow py-8">
    <div class="container mx-auto p-6 bg-white shadow-lg rounded-lg max-w-5xl">
      <div class="flex justify-between items-center mb-5">
        <button @click="toggleForm" class="bg-blue-500 text-white px-4 py-2 font-semibold text-sm rounded hover:bg-blue-600">
          {{ showForm ? 'Hide Task Form' : 'Show Task Form' }}
        </button>
      </div>

      <!-- Add Task Form -->
      <div v-if="showForm" class="mt-4 text-center">
        <input v-model="newTaskName" type="text" placeholder="Enter task name" class="border p-2 rounded w-full mb-2" />
        <button @click="addTask" class="bg-green-500 text-white px-4 py-2 rounded hover:bg-green-600" > Add Task </button>
      </div>

      <!-- Task Listing -->
      <div class="mt-6">
        <h2 class="text-2xl font-bold text-gray-800 mb-3">All Tasks</h2>

        <!-- Filtering Completed Tasks -->
        <div v-if="tasks.length > 0" class="my-5">
          <label class="inline-flex items-center">
            <input
                type="checkbox"
                v-model="showOnlyCompleted"
                class="mr-2"
            />
            Show only completed tasks
          </label>
        </div>
        <TaskList :tasks="tasks" :showOnlyCompleted="showOnlyCompleted" @delete-task="deleteTask" />
      </div>
    </div>
  </main>

  <!-- Footer Section -->
  <footer class="bg-gray-600 text-white p-4 fixed bottom-0 left-0 right-0">
    <div class="max-w-4xl mx-auto text-center">
      <p>&copy; 2024 Task Manager APP</p>
    </div>
  </footer>

</template>

<script setup>

import { ref, reactive, computed } from 'vue';
import TaskList from './components/TaskList.vue';

const tasks = reactive([]);
const showForm = ref(false);
const newTaskName = ref('');
const showOnlyCompleted = ref(false);

const toggleForm = () => {
  showForm.value = !showForm.value;
};

const addTask = () => {
  const name = newTaskName.value.trim();
  if (name.length < 3) {
    alert('Task name must be at least 3 characters long.');
    return;
  }
  tasks.push({ id: Date.now(), name, completed: false });
  newTaskName.value = '';
};

const deleteTask = (id) => {
  const index = tasks.findIndex((task) => task.id === id);
  if (index > -1) {
    tasks.splice(index, 1);
  }
};

</script>

<style scoped>

</style>
