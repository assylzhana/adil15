<template>
  <div class="custom-input-container">
    <div class="input-container">
      <label :for="inputId" class="input-label">Text:</label>
      <div class="input-wrapper">
        <input
          :type="type"
          :id="inputId"
          v-model="inputValue"
          @input="handleInput"
          :class="{ 'error-input': errorInput }"
          placeholder="Text"
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
    },
    inputId: {
      type: String,
      default: 'inputText'
    }
  },
  data() {
    return {
      inputValue: '',
      errorMessage: 'Required.',
      errorVisible: false,
      errorInput: false
    };
  },
  methods: {
    validateInput() {
      return !!this.inputValue.trim();
    },
    handleInput() {
      this.errorVisible = this.errorInput = this.inputValue === '';
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
