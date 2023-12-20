<template>
    <div v-if="isVisible" class="alert">
      <div class="alert-content">
        <p>{{ message }}</p>
        <button @click="closeAlert">Close</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isVisible: false,
        message: '',
      };
    },
    methods: {
      showAlert(message) {
        this.message = message;
        this.isVisible = true;
      },
      closeAlert() {
        this.isVisible = false;
      },
    },
  };
  </script>
  
  <style scoped>
  .alert {
    position: fixed;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    background-color: #f44336;
    color: white;
    padding: 15px;
    text-align: center;
    width: 80%;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    z-index: 1000;
  }
  
  .alert-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  button {
    background-color: #333;
    color: white;
    padding: 8px 12px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease-out;
  }
  
  button:hover {
    background-color: #555;
  }
  </style>
  