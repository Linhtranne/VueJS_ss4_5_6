<template>
    <div>
      <h1>bai 5</h1>
      <span>Mèn Mén loại 1, Số lượng {{data.data1}}</span> 
      <button @click="increase1">Tăng</button>
      <br>
      <span>Mèn Mén loại 2, Số lượng {{data.data2}}</span>
      <button @click="increase2">Tăng</button>
      <br>
      <span>Tổng: {{data.data1 + data.data2}}</span>
  
    </div>
  </template>
  
  <script setup>
  import { ref,reactive } from "vue";
  const data = reactive({
      data1: 1,
      data2: 1
  })
  
  function increase1() {
      data.data1++
     
  }
  function increase2() {
      data.data2++
  }
  
  </script>
  
  <style>
  
  </style>