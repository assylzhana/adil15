<template>
    <span :class="['label', colorClass]">
      {{ labelText }}
    </span>
  </template>
  
  <script>
  export default {
    props: {
      labelText: {
        type: String,
        required: true,
      },
      color: {
        type: String,
        default: 'default',
      },
    },
    computed: {
      colorClass() {
        return `label-${this.color}`;
      },
    },
  };
  </script>
  
  <style scoped>
  .label {
    display: inline-block;
    padding: 5px 10px;
    border-radius: 3px;
    font-size: 14px;
  }
  
  .label-default {
    background-color: #ccc;
    color: #333;
  }
  
  .label-primary {
    background-color: #2196f3;
    color: white;
  }
  
  .label-success {
    background-color: #4caf50;
    color: white;
  }
  
  .label-warning {
    background-color: #ff9800;
    color: white;
  }
  
  .label-danger {
    background-color: #f44336;
    color: white;
  }
  </style>
  