<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
      <h1>Bài 5</h1>
      <h2>Các số chẵn từ mảng:[1, 2, 3, 4, 5, 6, 7, 8, 9, 10] thì sẽ in ra kết quả là</h2>

        <div v-for="number in evenNumbers" :key="number">{{ number }}</div>

    </div>
  </template>
  
  <script setup>
  const array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

  const evenNumbers = array.filter((number) => number % 2 === 0);
  </script>

  