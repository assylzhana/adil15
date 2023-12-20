<template>
    <div class="card-container">
      <div class="card">
        <div class="card-header">
          <h2 class="card-title">{{ title }}</h2>
        </div>
        <div class="card-body">
          <img src="../../assets/front.png" alt="Card Image" class="card-image" />
          <p class="card-content">{{ content }}</p>
        </div>
        <div class="card-footer">
          <button v-if="showButton" @click="handleButtonClick" class="card-button">Click</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        required: true,
      },
      content: {
        type: String,
        required: true,
      },
      imageSrc: {
        type: String,
        required: true,
      },
      showButton: {
        type: Boolean,
        default: true,
      },
    },
    methods: {
      handleButtonClick() {
        console.log('Button clicked!');
      },
    },
  };
  </script>
  
  <style scoped>
  .card-container {
    max-width: 400px;
    margin: 20px auto;
  }
  
  .card {
    border: 1px solid #ccc;
    border-radius: 5px;
    overflow: hidden;
    transition: box-shadow 0.3s ease-out;
  }
  
  .card:hover {
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  
  .card-header {
    background-color: #2196f3;
    padding: 15px;
    color: white;
  }
  
  .card-title {
    margin: 0;
    font-size: 20px;
  }
  
  .card-body {
    padding: 20px;
  }
  
  .card-image {
    width: 100%;
    height: auto;
    border-radius: 5px;
    margin-bottom: 15px;
  }
  
  .card-content {
    margin: 0;
    font-size: 16px;
  }
  
  .card-footer {
    padding: 15px;
    text-align: right;
  }
  
  .card-button {
    background-color: #2196f3;
    color: white;
    padding: 10px 15px;
    font-size: 16px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease-out;
  }
  
  .card-button:hover {
    background-color: #0b7dda;
  }
  </style>
  