<template>
    <div class="toggle-container">
      <div class="input-container">
        <label class="toggle-label">
          <input
            type="checkbox"
            v-model="isChecked"
            @change="handleToggleChange"
            :class="{ 'error-input': errorInput }"
            class="custom-toggle"
          />
          <span class="toggle-slider"></span>
        </label>
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
        isChecked: false,
        errorMessage: 'Toggle must be switched on.',
        errorVisible: false,
        errorInput: false,
      };
    },
    methods: {
      validateToggle() {
        return this.isChecked;
      },
      handleToggleChange() {
        this.errorVisible = this.errorInput = !this.validateToggle();
      },
    },
  };
  </script>
  
  <style scoped>
  .toggle-container {
    max-width: 300px;
    margin: 20px auto;
  }
  
  .input-container {
    position: relative;
  }
  
  .toggle-label {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 34px;
  }
  
  .custom-toggle {
    opacity: 0;
    width: 0;
    height: 0;
  }
  
  .toggle-slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    border-radius: 34px;
    transition: 0.4s;
  }
  
  .custom-toggle:checked + .toggle-slider {
    background-color: #2196f3;
  }
  
  .toggle-slider:before {
    position: absolute;
    content: '';
    height: 26px;
    width: 26px;
    left: 4px;
    bottom: 4px;
    background-color: white;
    border-radius: 50%;
    transition: 0.4s;
  }
  
  .custom-toggle:checked + .toggle-slider:before {
    transform: translateX(26px);
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
    color: rgb(255, 47, 47);
  }
  </style>
  