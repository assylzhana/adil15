<template>
    <div class="dropdown-container">
      <div class="input-container">
        <div class="dropdown">
          <button
            @click="toggleDropdown"
            :class="{ 'active': isDropdownOpen }"
            class="custom-dropdown-button"
          >
            {{ selectedOption ? selectedOption : 'Select an option' }}
          </button>
          <div v-show="isDropdownOpen" class="dropdown-content">
            <div
              v-for="option in options"
              :key="option"
              @click="selectOption(option)"
              class="dropdown-item"
            >
              {{ option }}
            </div>
          </div>
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
        isDropdownOpen: false,
        selectedOption: null,
        options: ['Option 1', 'Option 2', 'Option 3'],
        errorMessage: 'Please select an option.',
        errorVisible: false,
      };
    },
    methods: {
      toggleDropdown() {
        this.isDropdownOpen = !this.isDropdownOpen;
      },
      selectOption(option) {
        this.selectedOption = option;
        this.isDropdownOpen = false;
        this.errorVisible = false;
      },
      validateDropdown() {
        return this.selectedOption !== null;
      },
    },
  };
  </script>
  
  <style scoped>
  .dropdown-container {
    max-width: 300px;
    margin: 20px auto;
  }
  
  .input-container {
    position: relative;
  }
  
  .custom-dropdown-button {
    padding: 10px;
    font-size: 16px;
    background-color: #2196f3;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease-out;
  }
  
  .custom-dropdown-button:hover {
    background-color: #0b7dda;
  }
  
  .dropdown {
    position: relative;
    display: inline-block;
  }
  
  .dropdown-content {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
    z-index: 1;
  }
  
  .dropdown-content .dropdown-item {
    padding: 12px 16px;
    display: block;
    cursor: pointer;
  }
  
  .dropdown-content .dropdown-item:hover {
    background-color: #ddd;
  }
  
  .active .dropdown-content {
    display: block;
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
  