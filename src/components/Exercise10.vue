<template>
    <div>
      <!-- Nút để hiển thị và ẩn nội dung -->
      <button @click="showContent">Hiển thị</button>
      <button @click="hideContent">Ẩn</button>
  
      <!-- Sử dụng v-if để hiển thị nội dung theo giá trị của isVisible -->
      <p v-if="isVisible">Nội dung được hiển thị</p>
      <p v-else>Nội dung bị ẩn</p>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // Tạo biến isVisible với giá trị mặc định là false
  const isVisible = ref(false);
  
  // Hàm để hiển thị nội dung
  const showContent = () => {
    isVisible.value = true;
  };
  
  // Hàm để ẩn nội dung
  const hideContent = () => {
    isVisible.value = false;
  };
  </script>
  
  <style scoped>
  button {
    margin-right: 10px;
    padding: 5px 10px;
    font-size: 14px;
    cursor: pointer;
  }
  
  p {
    font-size: 18px;
    font-weight: bold;
  }
  </style>
  