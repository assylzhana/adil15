<template>
    <div class="tabs">
      <div
        v-for="(tab, index) in tabs"
        :key="index"
        @click="changeTab(index)"
        :class="{ 'tab-item': true, 'active': index === activeTab }"
      >
        {{ tab.label }}
      </div>
  
      <div class="tab-content">
        <slot :tab="tabs[activeTab]"></slot>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        activeTab: 0,
        tabs: [
          { label: 'Tab 1', content: '1' },
          { label: 'Tab 2', content: '2' },
          { label: 'Tab 3', content: '3' },
        ],
      };
    },
    methods: {
      changeTab(index) {
        this.activeTab = index;
      },
    },
  };
  </script>
  
  <style scoped>
  .tabs {
    display: flex;
    flex-direction: column;
    max-width: 600px;
    margin: auto;
  }
  
  .tab-item {
    padding: 10px;
    cursor: pointer;
    border: 1px solid #ccc;
    border-bottom: none;
    border-radius: 5px 5px 0 0;
    background-color: #f9f9f9;
  }
  
  .tab-item.active {
    background-color: #fff;
  }
  
  .tab-content {
    border: 1px solid #ccc;
    border-radius: 0 0 5px 5px;
    padding: 10px;
    margin-top: -1px;
  }
  </style>
  