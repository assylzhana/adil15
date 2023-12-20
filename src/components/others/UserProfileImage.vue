<template>
    <div class="user-profile">
      <img src="../../assets/front.png" :src="profileImage" :alt="altText" class="profile-image" />
      <h3 class="user-name">{{ userName }}</h3>
      <p class="user-description">{{ userDescription }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      profileImage: {
        type: String,
        required: true,
      },
      altText: {
        type: String,
        default: 'User Profile Image',
      },
      userName: {
        type: String,
        required: true,
      },
      userDescription: {
        type: String,
        default: 'No description available.',
      },
    },
  };
  </script>
  
  <style scoped>
  
  .user-profile {
    text-align: center;
  }
  
  .profile-image {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
    margin-bottom: 10px;
  }
  
  .user-name {
    font-size: 1.2em;
    font-weight: bold;
    margin-bottom: 5px;
  }
  
  .user-description {
    color: #666;
    font-size: 0.9em;
  }
  </style>
  