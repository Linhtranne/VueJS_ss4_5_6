<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div>
        <h1>Bài 3</h1>
        <div v-if="role === 'admin'">Quyền hạn của bạn là <b>Admin</b></div>
        <div v-else-if="role === 'user'">Quyền hạn của bạn là <b>User</b></div>
        <div v-else-if="role === 'edit'">Quyền hạn của bạn là <b>Edit</b></div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
const role = ref('edit');
</script>


