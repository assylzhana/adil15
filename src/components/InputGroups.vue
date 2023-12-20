<template>
    <div class="input-group-container">
      <div class="input-group">
        <div class="input-group-prepend">
          <span class="input-addon">@</span>
        </div>
        <input
          type="text"
          v-model="username"
          @input="handleUsernameInput"
          :class="{ 'error-input': errors.username }"
          class="custom-input"
          placeholder="Username"
        />
        <button @click="handleButtonClick" class="addon-button">Go</button>
        <div class="error" v-if="errors.username">{{ errors.username }}</div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        username: '',
        errors: {},
      };
    },
    methods: {
      handleUsernameInput() {
        this.errors.username = ''; // Clear previous errors on input
      },
      handleButtonClick() {
        if (!this.username.trim()) {
          this.errors.username = 'Username is required';
        } else {
          // Perform the action you want when the button is clicked
          console.log('Button clicked with username:', this.username);
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .input-group-container {
    max-width: 300px;
    margin: 20px auto;
  }
  
  .input-group {
    display: flex;
  }
  
  .input-group-prepend {
    background-color: #ccc;
    padding: 10px;
    border-radius: 5px 0 0 5px;
    display: flex;
    align-items: center;
  }
  
  .input-addon {
    font-size: 16px;
  }
  
  .custom-input {
    flex: 1;
    padding: 10px;
    font-size: 16px;
    border: 2px solid #ccc;
    border-radius: 0 5px 5px 0;
    transition: border-color 0.3s ease-out;
  }
  
  .addon-button {
    background-color: #2196f3;
    color: white;
    padding: 10px 15px;
    font-size: 16px;
    border: none;
    border-radius: 0 5px 5px 0;
    cursor: pointer;
    transition: background-color 0.3s ease-out;
  }
  
  .addon-button:hover {
    background-color: #0b7dda;
  }
  
  .error {
    color: rgb(255, 47, 47);
    font-weight: bold;
    font-size: 13px;
    margin-top: 5px;
  }
  
  .error-input {
    border-color: rgb(255, 47, 47);
  }
  </style>
  