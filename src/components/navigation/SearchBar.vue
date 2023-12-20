<template>
    <div class="navigation-container">
  
      <div class="search-bar">
        <input type="text" placeholder="Search..." />
        <button>Search</button>
      </div>

    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isDrawerOpen: false,
      };
    },
    methods: {
      toggleDrawer() {
        this.isDrawerOpen = !this.isDrawerOpen;
      },
    },
  };
  </script>
  
  <style scoped>
  .navigation-container {
    max-width: 800px;
    margin: 20px auto;
  }
    .search-bar {
    display: flex;
    margin-bottom: 20px;
  }
  
  .search-bar input {
    flex: 1;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-right: 10px;
  }
  
  .search-bar button {
    background-color: #333;
    color: white;
    border: none;
    padding: 10px;
    border-radius: 5px;
    cursor: pointer;
  }
 
  </style>
  