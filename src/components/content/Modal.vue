<template>
    <div class="tooltip-container">
      <button @click="openModal" class="open-modal-button">Open Modal</button>
  
      <div v-if="isModalVisible" class="modal-overlay">
        <div class="modal">
          <span class="close" @click="closeModal">&times;</span>
          <div class="modal-content">
            <h2>Modal Title</h2>
            <p>This is the modal content.</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isModalVisible: false,
      };
    },
    methods: {
      openModal() {
        this.isModalVisible = true;
      },
      closeModal() {
        this.isModalVisible = false;
      },
    },
  };
  </script>
  
  <style scoped>
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
  }
  
  .modal {
    background: #fff;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    position: relative;
    max-width: 400px;
    width: 100%;
  }
  
  .close {
    position: absolute;
    top: 10px;
    right: 10px;
    font-size: 20px;
    color: #333;
    cursor: pointer;
  }
  
  .modal-content {
    text-align: center;
  }
  
  .open-modal-button {
    background-color: #2196f3;
    color: white;
    padding: 10px 15px;
    font-size: 16px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease-out;
  }
  
  .open-modal-button:hover {
    background-color: #0b7dda;
  }
  .tooltip-container {
    max-width: 400px;
    margin: 20px auto;
  }
  </style>
  