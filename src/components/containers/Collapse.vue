<template>
    <div class="collapse-container">
      <button @click="toggleCollapse" class="collapse-trigger">
        {{ collapsed ? 'Expand' : 'Collapse' }}
      </button>
      <div v-show="!collapsed" class="collapse-content">
        <p>So this is my collapse</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        collapsed: true,
      };
    },
    methods: {
      toggleCollapse() {
        this.collapsed = !this.collapsed;
      },
    },
  };
  </script>
  
  <style scoped>
  .collapse-container {
    max-width: 400px;
    margin: 20px auto;
  }
  
  .collapse-trigger {
    background-color: #2196f3;
    color: white;
    padding: 10px 15px;
    font-size: 16px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease-out;
  }
  
  .collapse-trigger:hover {
    background-color: #0b7dda;
  }
  
  .collapse-content {
    margin-top: 10px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  </style>
  