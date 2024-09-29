<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
        <h1>Bài 2</h1>
      <h2>Nếu isShow = {{ isShow }}</h2>
      <button @click="handleChange">
        <h1>{{ isShow ? 'Ẩn' : 'Hiện' }}</h1>
      </button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const isShow = ref(false);
  const handleChange = () => {
    isShow.value = !isShow.value;
  }
  </script>
  
  <style>

  </style>
  