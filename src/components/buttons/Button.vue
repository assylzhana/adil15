<template>
    <div class="button-container">
      <button
        @click="handleButtonClick"
        :class="{ 'error-button': errorInput }"
        class="custom-button"
      >
        Click me
      </button>
      <div class="error" :class="{ 'error-visible': errorVisible }">
        {{ errorMessage }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        errorMessage: 'Button cannot be clicked.',
        errorVisible: false,
        errorInput: false,
      };
    },
    methods: {
      validateButtonClick() {
      },
      handleButtonClick() {
        if (!this.validateButtonClick()) {
          this.errorVisible = this.errorInput = true;
        } else {
          alert('Button clicked!');
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .button-container {
    max-width: 300px;
    margin: 20px auto;
  }
  
  .custom-button {
    padding: 10px;
    font-size: 16px;
    background-color: #2196f3;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease-out;
  }
  
  .custom-button:hover {
    background-color: #0b7dda;
  }
  
  .error {
    color: rgb(255, 47, 47);
    font-weight: bold;
    font-size: 13px;
    margin-top: 5px;
    opacity: 0;
    transition: opacity 0.3s ease-out;
  }
  
  .error-visible {
    opacity: 1;
  }
  
  .error-button {
    background-color: #ff2f2f;
  }
  </style>
  