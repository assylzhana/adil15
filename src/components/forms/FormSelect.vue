<template>
    <div class="select-container">
      <div class="input-container">
        <label for="selectOption" class="input-label">Select Option:</label>
        <div class="input-wrapper">
          <select
            id="selectOption"
            v-model="selectedOption"
            @change="handleSelectChange"
            :class="{ 'error-input': errorInput }"
            class="select"
          >
            <option value="" disabled>Select an option</option>
            <option value="option1">Option 1</option>
            <option value="option2">Option 2</option>
            <option value="option3">Option 3</option>
          </select>
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
        selectedOption: '',
        errorMessage: 'Please select an option.',
        errorVisible: false,
        errorInput: false
      };
    },
    methods: {
      validateSelect() {
        return this.selectedOption !== '';
      },
      handleSelectChange() {
        this.errorVisible = this.errorInput = !this.validateSelect();
      }
    }
  };
  </script>
  
  <style scoped>
  .select-container {
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
  
  .select {
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
  