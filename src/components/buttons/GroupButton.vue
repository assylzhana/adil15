<template>
    <div class="group-button-container">
      <div class="input-container">
        <div class="group-buttons">
          <button
            v-for="button in buttons"
            :key="button.id"
            @click="handleButtonClick(button.id)"
            :class="{ 'active': selectedButton === button.id }"
            class="custom-group-button"
          >
            {{ button.label }}
          </button>
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
        buttons: [
          { id: 1, label: 'Button 1' },
          { id: 2, label: 'Button 2' },
          { id: 3, label: 'Button 3' },
        ],
        selectedButton: null,
        errorMessage: 'Please select a button.',
        errorVisible: false,
      };
    },
    methods: {
      handleButtonClick(buttonId) {
        this.selectedButton = buttonId;
        this.errorVisible = false;
      },
      validateGroupButton() {
        return this.selectedButton !== null;
      },
    },
  };
  </script>
  
  <style scoped>
  .group-button-container {
    max-width: 300px;
    margin: 20px auto;
  }
  
  .input-container {
    position: relative;
  }
  
  .custom-group-button {
    padding: 10px;
    font-size: 16px;
    background-color: #2195f3c5;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease-out;
  }
  
  .custom-group-button:hover {
    background-color: #0b7dda;
  }
  
  .group-buttons {
    display: flex;
  }
  
  .custom-group-button + .custom-group-button {
    margin-left: 5px;
  }
  
  .active {
    background-color: #0b7dda;
  }
  
  .active:hover {
    background-color: #0a5fae;
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
  </style>
  