<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
      <h1>Bài 8</h1>
      <div>
        <p>Mảng hiện tại: {{ currentNumbers.join(', ') }}</p>
      </div>
      <button @click="sortAsc">Tăng dần</button>
      <button @click="sortDesc">Giảm dần</button>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const originalNumbers = ref([5, 2, 9, 1, 5, 6]);
  const currentNumbers = ref([...originalNumbers.value]);
  
  const sortedAsc = computed(() => {
    return [...currentNumbers.value].sort((a, b) => a - b);
  });
  
  const sortedDesc = computed(() => {
    return [...currentNumbers.value].sort((a, b) => b - a);
  });
  
  const sortAsc = () => {
    currentNumbers.value = sortedAsc.value;
  };
  
  const sortDesc = () => {
    currentNumbers.value = sortedDesc.value;
  };
  </script>
  
  <style scoped>
  button {
    margin-right: 10px;
    padding: 10px 20px;
    font-size: 16px;
  }
  </style>
  