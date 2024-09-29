<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
      <h1>Bài 9</h1>
      <p>Giới tính hiện tại: {{ currentGender }}</p>
      <button @click="randomGender">Random gender</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const genders = ['Nam', 'Nữ', 'Khác'];
  const currentGender = ref('Nam');
  
  const randomGender = () => {
    const randomIndex = Math.floor(Math.random() * genders.length);
    currentGender.value = genders[randomIndex];
  };
  </script>
  
  