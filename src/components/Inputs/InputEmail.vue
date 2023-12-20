<template>
  <div class="email-input-container">
    <label for="inputEmail" class="input-label">Email:</label>
    <div class="input-wrapper">
      <input
        type="email"
        id="inputEmail"
        v-model="inputValue"
        @input="handleInput"
        :class="{ 'error-input': errorInput }"
        placeholder="Enter your email"
      />
      <div class="error-message" :class="{ 'error-visible': errorVisible }">
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
      errorMessage: 'Please enter a valid email address.',
      errorVisible: false,
      errorInput: false
    };
  },
  methods: {
    validateEmail(email) {
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      return emailRegex.test(email);
    },
    validateInput() {
      return this.validateEmail(this.inputValue.trim());
    },
    handleInput() {
      this.errorVisible = this.errorInput = !this.validateInput();
    }
  }
};
</script>

<style scoped>
.email-input-container {
  max-width: 300px;
  margin: 20px auto;
}

.input-label {
  display: block;
  margin-bottom: 5px;
  font-size: 18px;
}

.input-wrapper {
  position: relative;
}

input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border: 2px solid #ccc;
  border-radius: 5px;
  transition: border-color 0.3s ease-out;
}

.error-message {
  color: #ff4757;
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
  border-color: #ff4757;
}
</style>
