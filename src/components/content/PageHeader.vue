<template>
    <div class="page-header">
      <h1 class="header-title">{{ pageTitle }}</h1>
      <p class="header-subtitle">{{ pageSubtitle }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        pageTitle: 'Header',
        pageSubtitle: 'Subtitle',
      };
    },
  };
  </script>
  
  <style scoped>
  .page-header {
    text-align: center;
    margin: 20px 0;
  }
  
  .header-title {
    font-size: 32px;
    margin-bottom: 10px;
    color: #333;
  }
  
  .header-subtitle {
    font-size: 18px;
    color: #666;
  }
  </style>
  