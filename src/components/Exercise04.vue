<template>
    <div>
      <!-- Input để người dùng nhập giá trị -->
      <input type="text" v-model="inputValue" placeholder="Nhập văn bản" />
    </div>
  </template>
  
  <script setup>
  import { ref, watch } from 'vue';
  
  // Tạo một ref để lưu giá trị của input
  const inputValue = ref('');
  
  // Sử dụng watch để theo dõi sự thay đổi của inputValue
  watch(inputValue, (newValue, oldValue) => {
    console.log(`Giá trị thay đổi từ "${oldValue}" thành "${newValue}"`);
  });
  </script>
  
  <style scoped>
  input {
    padding: 10px;
    font-size: 16px;
    width: 300px;
    margin-top: 10px;
  }
  </style>
  