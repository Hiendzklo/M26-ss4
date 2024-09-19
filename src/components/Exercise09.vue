<template>
    <div>
      <h1>Danh sách bài viết</h1>
      <div v-for="(product, index) in products" :key="product.id" class="post">
        <p>Id: {{ product.id }}</p>
        <p>Title: {{ product.title }}</p>
        <p>Content: {{ product.content }}</p>
        <p>Author: {{ product.author }}</p>
        <hr />
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // Biến lưu trữ danh sách các bài viết
  const products = ref([
    {
      id: 1,
      title: 'Tại sao nên học ReactJS',
      content: 'Học ReactJS để đi làm',
      author: 'David',
    },
    {
      id: 2,
      title: 'Props trong ReactJS',
      content: 'Props giúp truyền dữ liệu từ component con xuống component cha',
      author: 'Linda',
    },
    {
      id: 3,
      title: 'State trong ReactJS là gì?',
      content: 'State giúp trữ trạng thái dữ liệu bên trong một component',
      author: 'David',
    },
  ]);
  </script>
  
  <style scoped>
  h1 {
    font-weight: bold;
    margin-bottom: 20px;
  }
  
  .post {
    margin-bottom: 20px;
  }
  
  hr {
    margin-top: 10px;
  }
  </style>
  