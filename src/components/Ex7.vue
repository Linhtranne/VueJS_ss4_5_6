<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
      <h1>Bài 7</h1>
      <div>
        <button
          :class="{ active: activeIndex === 1 }"
          @click="activeIndex = 1"
        >
          Button 1
        </button>
        <button
          :class="{ active: activeIndex === 2 }"
          @click="activeIndex = 2"
        >
          Button 2
        </button>
        <button
          :class="{ active: activeIndex === 3 }"
          @click="activeIndex = 3"
        >
          Button 3
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const activeIndex = ref(1);
  </script>
  
  <style scoped>
  .active {
    background-color: red;
    color: #fff;
  }
  button {
    margin-right: 10px;
    padding: 10px 20px;
    font-size: 16px;
  }
  </style>
  