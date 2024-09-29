<template>
    <div>
      <h1>Bài 4</h1>
      <input type="text" v-model="data">
    </div>
  </template>
  
  <script setup>
  import { ref ,watch} from "vue";
  const data = ref("")    
  
  watch(data, (newVal, oldVal) => {
      console.log(`data changed from ${oldVal} to ${newVal}`);
    })
  
  
  </script>
  
  <style>
  
  </style>