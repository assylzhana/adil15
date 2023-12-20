<template>
    <div class="list-group">
      <div v-for="(item, index) in items" :key="index" class="list-group-item">
        {{ item }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        items: ['Item 1', 'Item 2', 'Item 3', 'Item 4'],
      };
    },
  };
  </script>
  
  <style scoped>
  .list-group {
    width: 300px;
  }
  
  .list-group-item {
    background-color: #f4f4f4;
    padding: 10px;
    margin-bottom: 5px;
    border: 1px solid #ddd;
    border-radius: 4px;
    cursor: pointer;
  }
  
  .list-group-item:hover {
    background-color: #e0e0e0;
  }
  </style>
  