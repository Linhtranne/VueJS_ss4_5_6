<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
        <h1>Bài 4</h1>
      <h2>Khi giá trị của <b>isVisible = {{ isShow }}</b></h2>
      <button @click="handleChangeTrue()"><h1>Hiện</h1></button>
      <button @click="handleChangeFalse()"><h1>Ẩn</h1></button>
      <div v-if="isShow"><h2>Thông báo:<b>Welcome to Rikkei Academy</b></h2></div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const isShow = ref(false);
  const handleChangeTrue = () => {
    isShow.value = true;
  }
  const handleChangeFalse = () => {
    isShow.value = false;
  }
  </script>
  
  <style></style>