<script setup>
import sideNavigation from './components/sideNavigation.vue'
import profile from './components/profile.vue';
import heroBanner from './components/heroBanner.vue'
import taskCategories from './components/taskCategories.vue'
import taskList from './components/taskList.vue'
</script>

<template>
   <div class="container mx-auto">
    <div class="flex justify-between items-center">
    <button class="text-gray-600 p-1 rounded-[10px] border-solid border-2 border-[#f4f4f4] bg-white P-2">
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
      <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
    </svg>

    </button>

    <div class="flex items-center space-x-4">
      <img src="https://images.unsplash.com/photo-1491528323818-fdd1faba62cc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="Avatar" class="h-10 w-10 rounded-full border-solid border-2 border-[#f4f4f4]">
    </div>
  </div>

    <heroBanner/>

    <h2 class="text-neutral-500 font-bold">Categories</h2>
    <taskCategories/>
    
    <h2 class="text-neutral-500 font-bold my-4">You have 10 task for today</h2>
    <taskList/>
</div>

  

</template>

<style scoped>

</style>
