<script setup>
import {ref} from "vue";
const count = ref(0)
const handleIncrease = () =>{
    count.value++;
};
</script>

<template>
    <div>
        <h1>Bài 1</h1>
        <button @click="handleIncrease()"><h1>Click: {{count}} lần</h1></button>
    </div>
</template>

