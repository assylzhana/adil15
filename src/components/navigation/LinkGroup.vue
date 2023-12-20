<template>
    <div class="link-groups">
      <div class="link-group">
        <h3 class="group-title">Group 1</h3>
        <router-link to="/group1/link1" class="nav-link">Link 1</router-link>
        <router-link to="/group1/link2" class="nav-link">Link 2</router-link>
        <router-link to="/group1/link3" class="nav-link">Link 3</router-link>
      </div>
  
      <div class="link-group">
        <h3 class="group-title">Group 2</h3>
        <router-link to="/group2/link1" class="nav-link">Link 1</router-link>
        <router-link to="/group2/link2" class="nav-link">Link 2</router-link>
        <router-link to="/group2/link3" class="nav-link">Link 3</router-link>
      </div>
    </div>
  </template>

  <style scoped>
  .link-groups {
    display: flex;
    justify-content: space-between;
  }
  
  .link-group {
    width: 48%; 
  }
  
  .group-title {
    font-size: 18px;
    margin-bottom: 8px;
    color: #333;
  }
  
  .nav-link {
    display: block;
    text-decoration: none;
    color: #333;
    padding: 8px;
    transition: background-color 0.3s ease-out, color 0.3s ease-out;
  }
  
  .nav-link:hover {
    background-color: #eee;
    color: #555;
  }
  
  .nav-link.active {
    background-color: #ddd;
    color: #555;
  }
  </style>
  