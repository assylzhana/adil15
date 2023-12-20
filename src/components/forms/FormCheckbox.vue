<template>
    <div class="checkbox-container">
      <div class="input-container">
        <label class="checkbox-label">
          <input
            type="checkbox"
            v-model="isChecked"
            @change="handleCheckboxChange"
            :class="{ 'error-input': errorInput }"
            class="custom-checkbox"
          />
          Check me
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
        errorMessage: 'Checkbox must be checked.',
        errorVisible: false,
        errorInput: false,
      };
    },
    methods: {
      validateCheckbox() {
        return this.isChecked;
      },
      handleCheckboxChange() {
        this.errorVisible = this.errorInput = !this.validateCheckbox();
      },
    },
  };
  </script>
  
  <style scoped>
  .checkbox-container {
    max-width: 300px;
    margin: 20px auto;
  }
  
  .input-container {
    position: relative;
  }
  
  .checkbox-label {
    display: flex;
    align-items: center;
    font-size: 18px;
  }
  
  .custom-checkbox {
    margin-right: 10px;
    cursor: pointer;
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
  