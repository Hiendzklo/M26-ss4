<template>
    <div>
      <h1>Giỏ hàng</h1>
      <ul>
        <li v-for="(product, index) in cart" :key="index">
          {{ product.name }} - Số lượng: {{ product.quantity }}
          <button @click="increaseQuantity(index)">Tăng số lượng</button>
        </li>
      </ul>
      <h3>Tổng số lượng sản phẩm: {{ totalQuantity }}</h3>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  // Tạo danh sách sản phẩm trong giỏ hàng
  const cart = ref([
    { name: 'Mền Mền Loại 1', quantity: 3 },
    { name: 'Mền Mền Loại 2', quantity: 5 },
    { name: 'Mền Mền Loại 3', quantity: 1 }
  ]);
  
  // Hàm để tăng số lượng sản phẩm
  const increaseQuantity = (index) => {
    cart.value[index].quantity += 1;
  };
  
  // Sử dụng computed để tính tổng số lượng sản phẩm trong giỏ hàng
  const totalQuantity = computed(() => {
    return cart.value.reduce((total, product) => total + product.quantity, 0);
  });
  </script>
  
  <style scoped>
  button {
    margin-left: 10px;
    padding: 5px 10px;
    font-size: 14px;
    cursor: pointer;
  }
  </style>
  