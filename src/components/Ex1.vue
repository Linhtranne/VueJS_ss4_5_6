<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h1>Bài 1</h1>
    <h2>Khi giá trị của <b>isShow = {{ isShow }}</b></h2>
    <button @click="handleChange()"><h1>Hiện</h1></button>
    <div v-if="isShow">Rikkei Academy</div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const isShow = ref(false);
const handleChange = () => {
  isShow.value = true;
}
</script>

<style></style>
