<template>
    <div class="radiobox-container">
      <div class="input-container">
        <label for="customRadios" class="input-label">Choose option:</label>
        <label class="radiobox-label">
          <input
            type="radio"
            name="customRadios"
            v-model="selectedOption"
            :value="1"
            @change="handleRadioboxChange"
            :class="{ 'error-input': errorInput }"
            class="custom-radiobox"
          />
          Option 1
        </label>
        <label class="radiobox-label">
          <input
            type="radio"
            name="customRadios"
            v-model="selectedOption"
            :value="2"
            @change="handleRadioboxChange"
            :class="{ 'error-input': errorInput }"
            class="custom-radiobox"
          />
          Option 2
        </label>
        <label class="radiobox-label">
          <input
            type="radio"
            name="customRadios"
            v-model="selectedOption"
            :value="3"
            @change="handleRadioboxChange"
            :class="{ 'error-input': errorInput }"
            class="custom-radiobox"
          />
          Option 3
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
        selectedOption: null,
        errorMessage: 'Please select an option.',
        errorVisible: false,
        errorInput: false,
      };
    },
    methods: {
      validateRadiobox() {
        return this.selectedOption !== null;
      },
      handleRadioboxChange() {
        this.errorVisible = this.errorInput = !this.validateRadiobox();
      },
    },
  };
  </script>
  
  <style scoped>
  .radiobox-container {
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
  
  
  .radiobox-label {
    display: block;
    font-size: 18px;
    margin-bottom: 10px;
  }
  
  .custom-radiobox {
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
  