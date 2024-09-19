<template>
    <div>
      <h1>Giỏ hàng</h1>
      <ul>
        <!-- Lặp qua từng sản phẩm trong giỏ hàng và hiển thị tên và số lượng -->
        <li v-for="(product, index) in cart.items" :key="index">
          {{ product.name }} - Số lượng: {{ product.quantity }}
          <button @click="increaseQuantity(index)">Tăng số lượng</button>
        </li>
      </ul>
      <!-- Hiển thị tổng số lượng sản phẩm trong giỏ hàng -->
      <h3>Tổng số lượng sản phẩm: {{ totalQuantity }}</h3>
    </div>
  </template>
  
  <script setup>
  import { reactive, computed, watch } from 'vue';
  
  // Sử dụng reactive để lưu trạng thái giỏ hàng
  const cart = reactive({
    items: [
      { name: 'Mền Mền Loại 1', quantity: 3 },
      { name: 'Mền Mền Loại 2', quantity: 5 },
      { name: 'Mền Mền Loại 3', quantity: 1 }
    ]
  });
  
  // Tăng số lượng sản phẩm
  const increaseQuantity = (index) => {
    cart.items[index].quantity += 1;
  };
  
  // Tính tổng số lượng sản phẩm trong giỏ hàng
  const totalQuantity = computed(() => {
    return cart.items.reduce((total, product) => total + product.quantity, 0);
  });
  
  // Theo dõi sự thay đổi của giỏ hàng và log ra console mỗi khi giỏ hàng thay đổi
  watch(
    () => cart.items,
    (newVal, oldVal) => {
      console.log("Giỏ hàng đã thay đổi:", newVal);
    },
    { deep: true } // Theo dõi thay đổi sâu trong đối tượng giỏ hàng
  );
  </script>
  
  <style scoped>
  button {
    margin-left: 10px;
    padding: 5px 10px;
    font-size: 14px;
    cursor: pointer;
  }
  </style>
  