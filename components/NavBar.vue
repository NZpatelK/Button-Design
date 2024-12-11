<template>
    <nav class="navbar">
      <!-- <button
        @click="prevPage"
        :disabled="currentPage === 1"
        class="pagination-button"
      >
        Prev
      </button> -->
  
      <ul class="tabs">

        <li v-for="(tab, link) in links" :key="link" class="tab">
          <nuxt-link :to="tab" class="tab-link">{{ link }}</nuxt-link>
        </li>
      </ul>
  
      <!-- <button
        @click="nextPage"
        :disabled="currentPage === totalPages"
        class="pagination-button"
      >
        Next
      </button> -->
    </nav>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';

  const links = {
    'Download Button With Progress Bar': '/download-button-with-progress-bar',
    'Download Button With Circular Progress Bar': '/download-button-with-circular-progress-bar',
    'Aqua Button': '/aqua-button-effect',
  };
  
  // const tabs = Array.from({ length: 20 }, (_, i) => `Tab ${i + 1}`);
  // const tabsPerPage = 5;
  
  // const currentPage = ref(1);
  
  // const totalPages = computed(() => Math.ceil(tabs.length / tabsPerPage));
  
  // const visibleTabs = computed(() =>
  //   tabs.slice(
  //     (currentPage.value - 1) * tabsPerPage,
  //     currentPage.value * tabsPerPage
  //   )
  // );
  
  // const nextPage = () => {
  //   if (currentPage.value < totalPages.value) currentPage.value++;
  // };
  
  // const prevPage = () => {
  //   if (currentPage.value > 1) currentPage.value--;
  // };
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

  .navbar {
    position: absolute;
    bottom: 10rem;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Poppins', sans-serif;
    gap: 10px;
  }
  
  .tabs {
    display: flex;
    gap: 5px;
    list-style: none;
    background: linear-gradient(0deg, #efefef 0%, #ffffff 100%);
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.302);
    border-radius: 10px;
    padding: 20px 20px;
    margin: 0 40px;
    width: max-content;
  }
  
  .tab-link {
    position: relative;
    display: inline-block;
    font-size: 1rem;
    padding: 0 10px;
    text-decoration: none;
    text-transform: uppercase;
    color: #000000;
    z-index: 1;
  }



  .pagination-button {
    padding: 15px 40px;
    font-size: 1rem;
    border: 1px solid #ddd;
    background-color: #f0f0f0;
    cursor: pointer;
    border-radius: 4px;
  }
  
  .pagination-button:disabled {
    cursor: not-allowed;
    background-color: #ccc;
  }
  </style>
  