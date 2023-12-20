<template>
    <div class="breadcrumb">
      <span v-for="(item, index) in items" :key="index" :class="{ 'breadcrumb-item': true, 'active': index === items.length - 1 }">
        <router-link v-if="index !== items.length - 1" :to="item.to">{{ item.label }}</router-link>
        <span v-else>{{ item.label }}</span>
      </span>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      items: {
        type: Array,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>
  .breadcrumb {
    background-color: #f8f9fa;
    padding: 10px;
    margin: 10px 0;
    border-radius: 5px;
    font-size: 16px;
  }
  
  .breadcrumb-item {
    margin-right: 5px;
  }
  
  .breadcrumb-item a {
    color: #007bff;
    text-decoration: none;
  }
  
  .breadcrumb-item a:hover {
    text-decoration: underline;
  }
  
  .breadcrumb-item.active {
    color: #6c757d;
  }
  </style>
  