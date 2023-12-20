<template>
  <div class="custom-input-container">
    <div class="input-container">
      <label for="inputNumber" class="input-label">Number:</label>
      <div class="input-wrapper">
        <input
          :type="type"
          id="inputNumber"
          v-model="inputValue"
          @input="handleInput"
          :class="{ 'error-input': errorInput }"
          placeholder="Input Number"
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
  props: {
    type: {
      type: String,
      default: 'text'
    }
  },
  data() {
    return {
      inputValue: '',
      errorMessage: 'Enter a valid number.',
      errorVisible: false,
      errorInput: false
    };
  },
  methods: {
    validateNumber(number) {
      const numberRegex = /^\d+$/;
      return numberRegex.test(number);
    },
    validateInput() {
      return this.validateNumber(this.inputValue.trim());
    },
    handleInput() {
      this.errorVisible = this.errorInput = !this.validateInput();
    }
  }
};
</script>

<style scoped>
.custom-input-container {
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
