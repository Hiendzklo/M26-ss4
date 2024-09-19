<template>
    <div>
      <!-- Button hiển thị số lần nhấn -->
      <button @click="incrementCount">Click {{ count }} lần</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // Khởi tạo biến count với giá trị ban đầu là 0
  const count = ref(0);
  
  // Hàm xử lý sự kiện click, tăng giá trị của count lên 1
  const incrementCount = () => {
    count.value++; // Tăng giá trị count
  };
  </script>
  
  <style scoped>
  button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    margin: 10px 0;
  }
  </style>
  