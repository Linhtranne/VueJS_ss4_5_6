<template>
    <div>
      <h1>Bài 6</h1>
      <h2>Shopping Cart</h2>
      <input type="number" v-model.number="price" placeholder="Nhập giá sản phẩm"/> 
      <button @click="addToCart">Add to cart</button>
      <p>Tổng tiền trong giỏ hàng: {{ totalPrice }}</p>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const price = ref(0);
  const cartItems = ref([]);
  
  const addToCart = () => {
    cartItems.value.push(price.value);
    price.value = 0; 
  };
  
  const totalPrice = computed(() => {
    return cartItems.value.reduce((total, item) => total + item, 0);
  });
  </script>
  
  <style>
  </style>
  