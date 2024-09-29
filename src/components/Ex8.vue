<template>
    <div>
      <h1>bai 8</h1>
      <h2>Giỏ hàng</h2>
      
      <span>Sản phẩm Men 1, số lượng: {{ cartData.menQuantity }}</span> 
      <button @click="increaseMenQuantity">Tăng số lượng</button>
      <br>
  
      <span>Sản phẩm Women 1, số lượng: {{ cartData.womenQuantity }}</span>
      <button @click="increaseWomenQuantity">Tăng số lượng</button>
      <br>
  
      <span>Tổng cộng: {{ totalQuantity }}</span>
    </div>
  </template>
  
  <script setup>
  import { reactive, computed, watch } from 'vue';
  
  const cartData = reactive({
    menQuantity: 1,
    womenQuantity: 1,
  });
  
  const totalQuantity = computed(() => {
    return cartData.menQuantity + cartData.womenQuantity;
  });
  
  function increaseMenQuantity() {
    cartData.menQuantity++;
  }
  
  function increaseWomenQuantity() {
    cartData.womenQuantity++;
  }
  
  watch(
    () => cartData.menQuantity,
    (newVal, oldVal) => {
      console.log(`Số lượng sản phẩm Men 1 đã thay đổi từ ${oldVal} thành ${newVal}`);
    }
  );
  
  watch(
    () => cartData.womenQuantity,
    (newVal, oldVal) => {
      console.log(`Số lượng sản phẩm Women 1 đã thay đổi từ ${oldVal} thành ${newVal}`);
    }
  );
  </script>
  
  <style>
  </style>
  