<template>
    <div>
      <!-- Input cho người dùng nhập số -->
      <input type="number" v-model.number="number" placeholder="Nhập một số" />
  
      <!-- Hiển thị giá trị hiện tại của number -->
      <p>Giá trị hiện tại: {{ number }}</p>
  
      <!-- Hiển thị giá trị bình phương của number -->
      <p>Bình phương của số: {{ square }}</p>
    </div>
  </template>
  
  <script setup>
  import { ref, computed, watch } from 'vue';
  
  // Tạo biến ref để lưu giá trị của số nhập vào
  const number = ref(0);
  
  // Tạo thuộc tính computed để tính bình phương của số
  const square = computed(() => {
    return number.value * number.value;
  });
  
  // Sử dụng watch để theo dõi sự thay đổi của number và hiển thị thông báo trong console
  watch(number, (newValue, oldValue) => {
    console.log(`Giá trị thay đổi từ ${oldValue} thành ${newValue}`);
  });
  </script>
  
  <style scoped>
  input {
    padding: 5px;
    font-size: 14px;
    width: 150px;
    margin-bottom: 10px;
  }
  
  p {
    font-size: 16px;
    margin: 5px 0;
  }
  </style>
  