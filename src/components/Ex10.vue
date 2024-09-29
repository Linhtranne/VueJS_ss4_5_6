<template>
    <div>
        <h1>Bài 10</h1>
      <div>
        <p>Số nguyên hiện tại:</p>
        <ul>
          <li v-for="(number, index) in numbers" :key="index">{{ number }}</li>
        </ul>
      </div>

      <button @click="addRandomNumber">Random number</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const numbers = ref([]);
  
  const addRandomNumber = () => {
    const randomNumber = Math.floor(Math.random() * 100);
    numbers.value.push(randomNumber); 
  };
  </script>
  

  