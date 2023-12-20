<template>
    <div class="grid-container">
      <div class="grid-item" v-for="(item, index) in items" :key="index">
        {{ item }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        items: ['Grid 1', 'Grid 2', 'Grid 3', 'Grid 4', 'Grid 5'],
      };
    },
  };
  </script>
  
  <style scoped>
  .grid-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }
  
  .grid-item {
    width: calc(50% - 10px);
    margin-bottom: 20px;
    padding: 10px;
    border: 1px solid #ccc;
    box-sizing: border-box;
  }
  </style>
  