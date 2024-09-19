<template>
    <div>
      <h2>Company: {{ companyData.company }}</h2>
      <h3>Age: {{ companyData.age }}</h3>
      <button @click="changeData">Change data</button>
    </div>
  </template>
  
  <script setup>
  import { reactive } from 'vue';
  
  // Tạo đối tượng phản ứng với hai thuộc tính company và age
  const companyData = reactive({
    company: 'Rikkei Academy',
    age: 2,
  });
  
  // Hàm thay đổi giá trị của company và age khi nhấn nút
  const changeData = () => {
    companyData.company = 'Rikkei Education';
    companyData.age = 1;
  };
  </script>
  
  <style scoped>
  button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
  }
  </style>
  