<template>
    <div class="table-container">
      <table class="custom-table">
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Email</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="user in users" :key="user.id">
            <td>{{ user.id }}</td>
            <td>{{ user.name }}</td>
            <td>{{ user.email }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        users: [
          { id: 1, name: 'Adil', email: 'adil@gmail.com' },
          { id: 2, name: 'Alikhan', email: 'Alikhan@gmail.com' },
          { id: 3, name: 'Aruana', email: 'Aruana@gmail.com' },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .table-container {
    max-width: 600px;
    margin: 20px auto;
  }
  
  .custom-table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
  }
  
  .custom-table th,
  .custom-table td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: left;
  }
  
  .custom-table th {
    background-color: #f2f2f2;
  }
  </style>
  