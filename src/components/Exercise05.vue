<template>
    <div>
      <!-- Input cho người dùng nhập số tiền và button để thêm vào giỏ hàng -->
      <input type="number" v-model.number="inputValue" placeholder="Nhập số tiền" />
      <button @click="addToCart">Add to cart</button>
  
      <!-- Hiển thị tổng tiền trong giỏ hàng -->
      <h3>Tổng tiền trong giỏ hàng: {{ total }}</h3>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  // Biến lưu trữ giá trị nhập từ input
  const inputValue = ref(0);
  
  // Biến lưu trữ tổng tiền trong giỏ hàng
  const totalValue = ref(0);
  
  // Hàm để thêm giá trị từ input vào giỏ hàng
  const addToCart = () => {
    totalValue.value += inputValue.value; // Cộng giá trị từ input vào tổng tiền
    inputValue.value = 0; // Reset giá trị input về 0 sau khi thêm
  };
  
  // Computed để tính tổng tiền dựa trên giá trị hiện tại trong giỏ hàng
  const total = computed(() => {
    return totalValue.value;
  });
  </script>
  
  <style scoped>
  input {
    padding: 5px;
    font-size: 14px;
    width: 150px;
    margin-right: 10px;
  }
  
  button {
    padding: 5px 10px;
    font-size: 14px;
    cursor: pointer;
  }
  </style>
  