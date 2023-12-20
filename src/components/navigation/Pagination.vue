<template>
    <div>
      <ul class="item-list">
        <li v-for="item in paginatedItems" :key="item.id">{{ item.name }}</li>
      </ul>
  
      <div class="pagination">
        <button @click="previousPage" :disabled="currentPage === 1" class="pagination-btn">Previous</button>
        <span class="pagination-current">{{ currentPage }}</span>
        <button @click="nextPage" :disabled="currentPage === totalPages" class="pagination-btn">Next</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        items: [],
        itemsPerPage: 5,
        currentPage: 1,
      };
    },
    computed: {
      totalPages() {
        return Math.ceil(this.items.length / this.itemsPerPage);
      },
      paginatedItems() {
        const start = (this.currentPage - 1) * this.itemsPerPage;
        const end = start + this.itemsPerPage;
        return this.items.slice(start, end);
      },
    },
    methods: {
      nextPage() {
        if (this.currentPage < this.totalPages) {
          this.currentPage++;
        }
      },
      previousPage() {
        if (this.currentPage > 1) {
          this.currentPage--;
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .item-list {
    list-style: none;
    padding: 0;
  }
  
  .item-list li {
    background-color: #f4f4f4;
    margin-bottom: 5px;
    padding: 10px;
  }
  
  .pagination {
    margin-top: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .pagination-btn {
    cursor: pointer;
    padding: 8px 16px;
    margin: 0 5px;
    background-color: #3498db;
    color: #fff;
    border: none;
    border-radius: 4px;
    transition: background-color 0.3s ease;
  }
  
  .pagination-btn:hover {
    background-color: #2980b9;
  }
  
  .pagination-current {
    margin: 0 10px;
    font-size: 18px;
    font-weight: bold;
  }
  </style>
  