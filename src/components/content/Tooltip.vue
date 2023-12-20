<template>
    <div class="tooltip-container">
      <div @mouseover="showTooltip" @mouseleave="hideTooltip" class="tooltip-target">
        Tooltip
      </div>
      <div v-if="isTooltipVisible" class="tooltip">
        {{ tooltipText }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isTooltipVisible: false,
        tooltipText: 'This is a tooltip',
      };
    },
    methods: {
      showTooltip() {
        this.isTooltipVisible = true;
      },
      hideTooltip() {
        this.isTooltipVisible = false;
      },
    },
  };
  </script>
  
  <style scoped>
  .tooltip-container {
    max-width: 400px;
    margin: 20px auto;
    position: relative;
  }
  
  .tooltip-target {
    background-color: #2196f3;
    color: white;
    padding: 10px;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .tooltip {
    position: absolute;
    background-color: #333;
    color: white;
    padding: 5px;
    border-radius: 3px;
    top: 100%;
    left: 50%;
    transform: translateX(-50%);
    z-index: 1;
    white-space: nowrap;
  }
  </style>
  