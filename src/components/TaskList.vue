<template>
  <p v-if="filteredTasks.length === 0" class="text-center text-gray-500 border rounded p-4">
    No tasks available
  </p>
  <ul>
    <li v-for="task in filteredTasks" :key="task.id" :class="taskClass(task)" class="p-4 mb-2 border rounded flex justify-between items-center">
      <div>
        <input type="checkbox" v-model="task.completed" class="mr-2" />
        <span>{{ task.name }}</span>
      </div>
      <button @click="$emit('delete-task', task.id)" class="text-red-500 hover:text-red-700">Delete</button>
    </li>
  </ul>
</template>

<script setup>
import { computed, toRefs } from 'vue';

const emits = defineEmits(['delete-task']);

const props = defineProps({
  tasks: Array,
  showOnlyCompleted: Boolean,
});

const filteredTasks = computed(() => {
  return props.showOnlyCompleted
      ? props.tasks.filter((task) => task.completed)
      : props.tasks;
});

const taskClass = (task) =>
    task.completed
        ? 'bg-green-100 border-red-500'
        : 'bg-white border-gray-300';
</script>
