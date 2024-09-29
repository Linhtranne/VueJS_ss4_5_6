<template>
    <div>
      <h1>Bài 3</h1>
      <p>Diện tích : {{data.with*data.height}}</p>
      <button @click="changeData2">change data</button>
    </div>
  </template>
  
  <script setup>
  import { reactive } from "vue";
  
  const data = reactive({
      with : 10,
      height : 20
  })
  
  const changeData2 = () => {
      data.with = Math.floor(Math.random() * 100)
      data.height = Math.floor(Math.random() * 100)
  }
  </script>
  
  <style>
  
  </style>