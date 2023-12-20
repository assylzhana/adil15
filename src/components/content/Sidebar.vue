<template>
    <div class="page-container">
      <div class="page-sidebar">
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <li><router-link to="/services">Services</router-link></li>
          <li><router-link to="/contact">Contact</router-link></li>
        </ul>
      </div>
      <div class="page-content">
        <router-view></router-view>
      </div>
    </div>
  </template>
  
  <style scoped>
  .page-container {
    display: flex;
  }
  
  .page-sidebar {
    width: 250px;
    background-color: #333;
    color: white;
    padding: 30px;
    transition: width 0.3s ease-in-out;
  }
  
  .page-sidebar:hover {
    width: 270px;
  }
  
  .page-sidebar ul {
    list-style: none;
    padding: 0;
  }
  
  .page-sidebar li {
    margin-bottom: 15px;
    transition: background-color 0.3s ease-in-out;
  }
  
  .page-sidebar li:hover {
    background-color: #555;
  }
  
  .page-sidebar a {
    text-decoration: none;
    color: white;
    font-size: 18px;
    transition: color 0.3s ease-in-out;
  }
  
  .page-sidebar a:hover {
    color: #ffd700;
  }
  
  .page-content {
    flex: 1;
    padding: 30px;
    font-size: 18px;
  }
  </style>
  