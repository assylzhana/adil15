<template>
  <div class="password-input-container">
    <div class="input-container">
      <label for="inputPassword" class="input-label">Password:</label>
      <input
        :type="showPassword ? 'text' : 'password'"
        name="inputPassword"
        id="inputPassword"
        v-model="inputValue"
        @input="handleInput"
        :class="{ 'error-input': errorInput }"
        placeholder="Enter Password"
        class="password-input"
      />
      <button @click="togglePasswordVisibility" class="password-toggle-button">
      </button>
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
      errorMessage: 'Password must be at least 8 characters.',
      errorVisible: false,
      errorInput: false,
      showPassword: false
    };
  },
  methods: {
    validatePassword(password) {
      // Password validation logic (e.g., minimum length)
      return password.length >= 8;
    },
    validateInput() {
      return this.validatePassword(this.inputValue.trim());
    },
    handleInput() {
      this.errorVisible = this.errorInput = !this.validateInput();
    },
    togglePasswordVisibility() {
      this.showPassword = !this.showPassword;
    }
  }
};
</script>

<style scoped>
.password-input-container {
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

.password-input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border: 2px solid #ccc;
  border-radius: 5px;
  transition: border-color 0.3s ease-out;
}

.password-toggle-button {
  position: absolute;
  right: 5px;
  top: 50%;
  font-size: 16px;
  transform: translateY(-50%);
  cursor: pointer;
  background: none;
  border: none;
}

.error {
  color: rgb(255, 47, 47);
  font-weight: bold;
  font-size: 13px;
  position: absolute;
  bottom: -20px;
  opacity: 0;
  transition: top 0.3s ease-out, opacity 0.3s ease-out;
  z-index: 1;
}

.error-visible {
  opacity: 1;
}
</style>
