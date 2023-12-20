<template>
    <div class="accordion-container">
      <div v-for="(item, index) in accordionItems" :key="index" class="accordion-item">
        <div @click="toggleAccordion(index)" class="accordion-title">
          {{ item.title }}
          <span :class="{ 'rotate-arrow': activeIndex === index }">&#9658;</span>
        </div>
        <div v-show="activeIndex === index" class="accordion-content">
          {{ item.content }}
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        activeIndex: null,
        accordionItems: [
          { title: 'Accordion 1', content: 'Content 1.' },
          { title: 'Accordion 2', content: 'Content 2.' },
          { title: 'Accordion 3', content: 'Content 3.' },
        ],
      };
    },
    methods: {
      toggleAccordion(index) {
        this.activeIndex = this.activeIndex === index ? null : index;
      },
    },
  };
  </script>
  
  <style scoped>
  .accordion-container {
    max-width: 600px;
    margin: 20px auto;
  }
  
  .accordion-item {
    border: 1px solid #ccc;
    border-radius: 5px;
    overflow: hidden;
    margin-bottom: 10px;
  }
  
  .accordion-title {
    background-color: #f1f1f1;
    padding: 10px;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .rotate-arrow {
    transform: rotate(90deg);
    transition: transform 0.3s ease-out;
  }
  
  .accordion-content {
    padding: 10px;
  }
  </style>
  