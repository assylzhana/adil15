<template>
    <div class="image-carousel">
      <div class="carousel-container">
        <div v-for="(image, index) in images" :key="index" :class="{ 'carousel-slide': true, 'active-slide': index === currentIndex }">
          <img :src="image" alt="Slide" class="carousel-image" />
        </div>
      </div>
      <button @click="prevSlide" class="carousel-control prev">Previous</button>
      <button @click="nextSlide" class="carousel-control next">Next</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        images: [
          'https://www.w3.org/html/logo/downloads/HTML5_1Color_Black.png',
          'https://www.w3.org/StyleSheets/TR/logo-favicon.png',
          'https://www.w3.org/Icons/w3c_home',
          'https://www.w3.org/Icons/w3c_logo',
        ],
        currentIndex: 0,
      };
    },
    methods: {
      nextSlide() {
        this.currentIndex = (this.currentIndex + 1) % this.images.length;
      },
      prevSlide() {
        this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
      },
    },
  };
  </script>
  
  
  
  
  <style scoped>
  .image-carousel {
    position: relative;
    width: 80%;
    margin: auto;
  }
  
  .carousel-container {
    display: flex;
    overflow: hidden;
  }
  
  .carousel-slide {
    flex: 0 0 100%;
    transition: transform 0.5s ease-in-out;
  }
  
  .active-slide {
    transform: translateX(-100%);
  }
  
  .carousel-image {
    width: 100%;
  }
  
  .carousel-control {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: #333;
    color: white;
    padding: 10px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    transition: background-color 0.3s ease-out;
  }
  
  .carousel-control:hover {
    background-color: #555;
  }
  
  .prev {
    left: 10px;
  }
  
  .next {
    right: 10px;
  }
  </style>
  