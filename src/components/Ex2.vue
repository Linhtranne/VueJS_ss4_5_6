<template>
    <div>
        <h1>Bài 2</h1>
      <h3>Company: {{ state.company }}</h3>
      <h4>Age: {{ state.age }}</h4>
      <button @click="changeData()">Change data</button>
    </div>
  </template>
  <script setup>
  import { reactive } from 'vue';

      const state = reactive({
        company: 'Rikkei Academy',
        age: 2
      });
      const changeData = () => {
        state.company = 'Rikkei Education';
        state.age = 1;
      };
  
  </script>
  
  <style>


  </style>
  