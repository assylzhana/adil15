<template>
  <div class="list-container">
    <ul class="custom-list">
      <li v-for="item in items" :key="item.id" class="list-item">
        {{ item.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { id: 1, name: 'Item 1' },
        { id: 2, name: 'Item 2' },
        { id: 3, name: 'Item 3' },
      ],
    };
  },
};
</script>

<style scoped>
.list-container {
  max-width: 400px;
  margin: 20px auto;
}

.custom-list {
  list-style: none;
  padding: 0;
}

.list-item {
  background-color: #f8f8f8;
  border: 1px solid #ddd;
  padding: 15px;
  margin-bottom: 8px;
  border-radius: 5px;
  transition: background-color 0.3s ease-out;
}

.list-item:hover {
  background-color: #e0e0e0;
}
</style>
