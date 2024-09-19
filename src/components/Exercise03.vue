<template>
    <div>
      <h2>Acreage: {{ acreage }}</h2>
      <button @click="increaseWidth">Increase width</button>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  // Khởi tạo hai biến width và height
  const width = ref(10);
  const height = ref(20);
  
  // Tạo thuộc tính computed để tính diện tích
  const acreage = computed(() => {
    return width.value * height.value;
  });
  
  // Hàm xử lý khi người dùng nhấn nút, tăng giá trị của width
  const increaseWidth = () => {
    width.value += 10;
  };
  </script>
  
  <style scoped>
  button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    margin-top: 10px;
  }
  </style>
  