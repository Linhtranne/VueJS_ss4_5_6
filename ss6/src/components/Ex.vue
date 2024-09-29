<template>
    <div class="container">
      <form @submit.prevent="onSubmit" class="form">
        <div class="nav">
          <input type="text" placeholder="Enter your job" v-model="valueInput" class="input-task" />
          <button
            type="submit"
            @click="addTask"
            class="btn-add"
          >
            Add Job
          </button>
        </div>
        <div v-if="notify" class="error-message">Công việc không được để trống</div>
        <div v-if="filterList.length > 0" class="list">
          <div class="list-item" :class="{ completed: btn.status }" v-for="(btn, index) in filterList" :key="index">
            <div class="task-detail">
              <input
                @click="handleTask(btn.id)"
                :checked="btn.status"
                type="checkbox"
              />
              <span>{{ btn.detail }}</span>
            </div>
            <button
              @click="handleDelete(btn.id)"
              class="btn-delete"
            >
              Delete
            </button>
          </div>
        </div>
        <p class="task-summary">
          Số công việc hoàn thành:{{ taskDone }}/{{ list.length }} công việc
        </p>
      </form>
    </div>
  </template>
  
  <script setup>
  import { computed, ref, watch } from "vue";
  
  const list = ref(JSON.parse(localStorage.getItem("listTask")) || []);
  const valueInput = ref("");
  const taskDone = computed(() => list.value.filter((btn) => btn.status).length);
  const filterList = computed(() => list.value);
  const notify = ref(false);
  
  watch(valueInput, () => {
    notify.value = false;
  });
  
  const addTask = () => {
    if (valueInput.value) {
      let newTask = {
        id: Math.floor(Math.random() * 100000000),
        detail: valueInput.value,
        status: false,
      };
      list.value.push(newTask);
      localStorage.setItem("listTask", JSON.stringify(list.value));
      valueInput.value = "";
    } else {
      notify.value = true;
    }
  };
  
  const handleDelete = (id) => {
    list.value = list.value.filter((btn) => btn.id !== id);
    localStorage.setItem("listTask", JSON.stringify(list.value));
  };
  
  const handleTask = (id) => {
    list.value = list.value.map((btn) =>
      btn.id === id ? { ...btn, status: !btn.status } : btn
    );
    localStorage.setItem("listTask", JSON.stringify(list.value));
  };
  </script>
  
  <style scoped>
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .form {
    display: flex;
    flex-direction: column;
    gap: 10px;
    width: 400px;
    padding: 10px;
    border: 1px solid rgb(207, 203, 203);
    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);
    border-radius: 5px;
    background-color: #fff;
  }
  
  .nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .input-task {
    flex: 1;
    padding: 10px;
    border: 1px solid rgb(198, 190, 190);
    border-radius: 5px;
    margin-right: 10px;
  }
  
  .input-task:focus {
    outline: none;
  }
  
  .btn-add {
    padding: 10px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .btn-add:hover {
    background-color: #0056b3;
  }
  
  .error-message {
    color: red;
    font-size: 14px;
  }
  
  .list {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  
  .list-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  .task-detail {
    display: flex;
    gap: 10px;
    align-items: center;
  }
  
  .completed span {
    text-decoration: line-through;
    color: #999;
  }
  
  .btn-delete {
    background-color: red;
    color: white;
    border: none;
    padding: 8px 12px;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .btn-delete:hover {
    background-color: darkred;
  }
  
  .task-summary {
    background-color: rgb(198, 190, 190);
    padding: 5px;
    text-align: center;
    border-radius: 5px;
  }
  </style>
  