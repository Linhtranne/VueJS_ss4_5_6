<template>
    <div>
      <h1>Bài 7</h1>
      <input type="number" v-model.number="myValue"/> 
      <button @click="addToCart">Add to cart</button>
      <p>Giá trị hiện tại: {{ price}}</p>
      <p>Giá trị bình phương {{powerPrice}}</p>
    </div>
  </template>
  
  <script setup>
  import { ref, computed, watch } from 'vue';
  const myValue = ref (0)
  const price = ref(0);

  watch(price, (newValue, oldValue) => {
    console.log(`data changed from ${oldValue} to ${newValue}`);
  })


  const addToCart = () => {
    price.value = myValue.value 
    myValue.value = 0; 
  };
  
  const powerPrice = computed(() => {
    return price.value*price.value 
  });
  </script>
  
  <style>
  </style>
  