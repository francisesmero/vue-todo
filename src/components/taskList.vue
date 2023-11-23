<template>
  <h2 class="text-neutral-500 font-bold mb-4">
    You have {{ totalItems }} task for today
  </h2>

  <div
    class="card-todo flex flex-row gap-x-2"
    v-for="todo in sortedTodos"
    :key="todo.id"
  >
    <div
      class="w-full card-item bg-white p-4 flex flex-row justify-between items-center rounded-[15px] my-2"
    >
      <div class="flex items-center space-x-4">
        <span
          class="rounded-full p-2 w-2 h-2"
          :class="{
            'bg-red-500': todo.todoCategory === 'health',
            'bg-gradient-primary': todo.todoCategory === 'work',
            'bg-orange-400': todo.todoCategory === 'personal',
            'bg-green-300': todo.todoCategory === 'shopping',
          }"
        ></span>
        <p class="text-neutral-600 ml-6"><span class="mr-2">{{ todo.id }}.)</span>{{ todo.todoItem }} </p> 
      </div>

      <div class="flex items-center space-x-4">
        <p class="text-neutral-500">{{ todo.todoTime }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, computed } from "vue";
import data from "../../data.json";

const todos = ref([]);

onMounted(() => {
  todos.value = data.todos;
});

const sortedTodos = computed(() => {
  return todos.value.slice().sort((a, b) => {
    const timeA = a.todoTime.split(":").map(Number);
    const timeB = b.todoTime.split(":").map(Number);

    if (timeA[0] !== timeB[0]) {
      return timeA[0] - timeB[0];
    }

    return timeA[1] - timeB[1];
  });
});

const totalItems = computed(() => sortedTodos.value.length);
</script>

<style lang="scss" scoped></style>
