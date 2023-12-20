<template>
    <div class="slider-container">
      <div class="input-container">
        <label for="sliderInput" class="input-label">Slider Value: {{ sliderValue }}</label>
        <input
          type="range"
          id="sliderInput"
          v-model="sliderValue"
          @input="handleSliderChange"
          :class="{ 'error-input': errorInput }"
          class="custom-slider"
        />
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
        sliderValue: 50,
        errorMessage: 'Please adjust the slider.',
        errorVisible: false,
        errorInput: false,
      };
    },
    methods: {
      handleSliderChange() {
        this.errorVisible = this.errorInput = !this.validateSlider();
      },
      validateSlider() {
        // Add your slider validation logic here
        // For example, you can check some conditions before allowing the slider change.
        return true; // For demonstration purposes, always allow the slider change.
      },
    },
  };
  </script>
  
  <style scoped>
  .slider-container {
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
  
  .custom-slider {
    width: 100%;
    margin-top: 10px;
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
  
  .error-input {
    color: rgb(255, 47, 47);
  }
  </style>
  