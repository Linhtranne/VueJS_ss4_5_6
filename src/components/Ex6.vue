<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
      <h1>Bài 6</h1>
      <h2>Các số chẵn từ mảng:[5 ,12 ,15, 22 ,9 ,18 ,25 ,30 ,7 ,33] thì sẽ in ra kết quả là</h2>

        <div v-for="number in evenNumbers" :key="number">{{ number }}</div>

    </div>
  </template>
  
  <script setup>
  const array = [5 ,12 ,15, 22 ,9 ,18 ,25 ,30 ,7 ,33];

  const evenNumbers = array.filter((number) => number % 2 === 1);
  </script>

  