<template>
  <div class="my-4 p-8 flex flex-row rounded-[15px] bg-gradient-primary">
    <h1 class="text-xl text-white basis-1/2 leading-6 self-center">
      Manage your time well, <span class="font-bold">Francis</span>
    </h1>

    <img
      src="../assets/asset_1.svg"
      class="basis-1/2 w-[80px] h-[80px] self-center"
    />
  </div>
</template>

<script setup>
import { ref, onMounted, computed, watch } from "vue";

watch(name, (newName) => {
  localStorage.setItem("name", newName);
});
</script>

<style lang="scss" scoped></style>
