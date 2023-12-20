<template>
    <div class="navigation-container">
        <div class="navbar">
      <a href="#">Home</a>
      <a href="#">About</a>
      <a href="#">Services</a>
      <a href="#">Contact</a>
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
   .navbar {
    background-color: #333;
    padding: 10px;
    border-radius: 5px;
    margin-bottom: 20px;
  }
  
  .navbar a {
    color: white;
    text-decoration: none;
    margin-right: 10px;
  }
  
  </style>
  