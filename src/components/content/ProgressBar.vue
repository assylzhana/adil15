<template>
    <div class="progress-bar-container">
      <div class="progress-bar">
        <div :style="{ width: `${progress}%` }" class="progress-bar-fill"></div>
      </div>
      <div class="progress-info">
        {{ progress }}%
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      progress: {
        type: Number,
        required: true,
        validator: (value) => value >= 0 && value <= 100,
      },
    },
  };
  </script>
  
  <style scoped>
  .progress-bar-container {
    max-width: 400px;
    margin: 20px auto;
  }
  
  .progress-bar {
    width: 100%;
    height: 20px;
    background-color: #eee;
    border-radius: 5px;
    overflow: hidden;
    margin-bottom: 10px;
  }
  
  .progress-bar-fill {
    height: 100%;
    background-color: #2196f3;
    transition: width 0.3s ease-out;
  }
  
  .progress-info {
    text-align: center;
    font-size: 16px;
    color: #333;
  }
  </style>
  