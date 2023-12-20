<template>
    <div class="custom-datetime-picker">
      <div class="input-container">
        <label for="inputDateTime" class="input-label">Date & Time:</label>
        <div class="input-wrapper">
          <input
            type="datetime-local"
            id="inputDateTime"
            v-model="inputValue"
            @input="handleInput"
            :class="{ 'error-input': errorInput }"
            class="custom-input"
          />
        </div>
        <div class="error" :class="{ 'error-visible': errorVisible }">
          {{ errorMessage }}
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        inputValue: '',
        errorMessage: 'Enter a valid date and time.',
        errorVisible: false,
        errorInput: false
      };
    },
    methods: {
      validateDateTime(dateTime) {
        // You can add more advanced validation logic if needed
        return dateTime !== '';
      },
      validateInput() {
        return this.validateDateTime(this.inputValue);
      },
      handleInput() {
        this.errorVisible = this.errorInput = !this.validateInput();
      }
    }
  };
  </script>
  
  <style scoped>
  .custom-datetime-picker {
    max-width: 300px;
    margin: 20px auto;
  }
  
  .input-container {
    position: relative;
  }
  
  .input-label {
    display: block;
    margin-bottom: 5px;
    font-size: 18px;
  }
  
  .input-wrapper {
    position: relative;
  }
  
  .custom-input {
    width: 100%;
    padding: 10px;
    font-size: 16px;
    border: 2px solid #ccc;
    border-radius: 5px;
    transition: border-color 0.3s ease-out;
  }
  
  .error {
    color: rgb(255, 47, 47);
    font-weight: bold;
    font-size: 13px;
    position: absolute;
    top: 100%;
    left: 0;
    opacity: 0;
    transition: opacity 0.3s ease-out;
  }
  
  .error-visible {
    opacity: 1;
  }
  
  .error-input {
    border-color: rgb(255, 47, 47);
  }
  </style>
  