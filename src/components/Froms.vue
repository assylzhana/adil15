<template>
    <div class="form-container">
      <form @submit.prevent="submitForm">
        <div class="input-container">
          <label for="name" class="input-label">Name:</label>
          <input
            type="text"
            id="name"
            v-model="formData.name"
            :class="{ 'error-input': errors.name }"
            class="custom-input"
            placeholder="Enter your name"
          />
          <div class="error" v-if="errors.name">{{ errors.name }}</div>
        </div>
  
        <div class="input-container">
          <label for="email" class="input-label">Email:</label>
          <input
            type="email"
            id="email"
            v-model="formData.email"
            :class="{ 'error-input': errors.email }"
            class="custom-input"
            placeholder="Enter your email"
          />
          <div class="error" v-if="errors.email">{{ errors.email }}</div>
        </div>
  
        <div class="input-container">
          <label for="message" class="input-label">Message:</label>
          <textarea
            id="message"
            v-model="formData.message"
            :class="{ 'error-input': errors.message }"
            class="custom-textarea"
            placeholder="Type your message"
          ></textarea>
          <div class="error" v-if="errors.message">{{ errors.message }}</div>
        </div>
  
        <div class="input-container">
          <label class="input-label">Gender:</label>
          <div class="radio-group">
            <label>
              <input
                type="radio"
                v-model="formData.gender"
                value="male"
                :class="{ 'error-input': errors.gender }"
              />
              Male
            </label>
            <label>
              <input
                type="radio"
                v-model="formData.gender"
                value="female"
                :class="{ 'error-input': errors.gender }"
              />
              Female
            </label>
          </div>
          <div class="error" v-if="errors.gender">{{ errors.gender }}</div>
        </div>
  
        <div class="input-container">
          <label for="country" class="input-label">Country:</label>
          <select
            id="country"
            v-model="formData.country"
            :class="{ 'error-input': errors.country }"
            class="custom-select"
          >
            <option value="" disabled>Select your country</option>
            <option value="usa">USA</option>
            <option value="canada">Canada</option>
            <option value="uk">UK</option>
          </select>
          <div class="error" v-if="errors.country">{{ errors.country }}</div>
        </div>
  
        <button type="submit" class="submit-button">Submit</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        formData: {
          name: '',
          email: '',
          message: '',
          gender: '',
          country: '',
        },
        errors: {},
      };
    },
    methods: {
      submitForm() {
        this.errors = {}; // Reset errors on each submit
  
        // Validate form fields
        if (!this.formData.name.trim()) {
          this.errors.name = 'Name is required';
        }
  
        if (!this.formData.email.trim()) {
          this.errors.email = 'Email is required';
        } else if (!this.isValidEmail(this.formData.email)) {
          this.errors.email = 'Invalid email format';
        }
  
        if (!this.formData.message.trim()) {
          this.errors.message = 'Message is required';
        }
  
        if (!this.formData.gender) {
          this.errors.gender = 'Gender is required';
        }
  
        if (!this.formData.country) {
          this.errors.country = 'Country is required';
        }
  
        // If no errors, you can proceed with form submission
        if (Object.keys(this.errors).length === 0) {
          // Perform form submission or any other action here
          console.log('Form submitted successfully!');
        }
      },
      isValidEmail(email) {
        // Basic email validation
        const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return emailRegex.test(email);
      },
    },
  };
  </script>
  
  <style scoped>
  .form-container {
    max-width: 500px;
    margin: 20px auto;
  }
  
  .input-container {
    margin-bottom: 20px;
  }
  
  .input-label {
    display: block;
    margin-bottom: 5px;
    font-size: 18px;
  }
  
  .custom-input,
  .custom-textarea,
  .custom-select {
    width: 100%;
    padding: 10px;
    font-size: 16px;
    border: 2px solid #ccc;
    border-radius: 5px;
    transition: border-color 0.3s ease-out;
  }
  
  .custom-textarea {
    resize: vertical;
  }
  
  .radio-group {
    display: flex;
    margin-top: 5px;
  }
  
  .radio-group label {
    margin-right: 20px;
  }
  
  .submit-button {
    background-color: #2196f3;
    color: white;
    padding: 10px 20px;
    font-size: 18px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease-out;
  }
  
  .submit-button:hover {
    background-color: #0b7dda;
  }
  
  .error {
    color: rgb(255, 47, 47);
    font-weight: bold;
    font-size: 13px;
    margin-top: 5px;
  }
  
  .error-input {
    border-color: rgb(255, 47, 47);
  }
  </style>
  