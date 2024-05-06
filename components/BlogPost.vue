<template>
    <div class="container mx-auto px-4 py-8">
      <div class="max-w-4xl mx-auto bg-white shadow-lg rounded-lg overflow-hidden">
        <!-- Article Image -->
        <img class="w-full h-auto" src="https://img.freepik.com/premium-photo/high-angle-view-software-developer-writing-code-while-using-computer-data-systems-office_236854-44145.jpg?size=626&ext=jpg&ga=GA1.1.553209589.1714867200&semt=sph" :alt="title" />
  
        <!-- Article Content -->
        <div class="p-6">
          <!-- Article Title -->
          <h1 class="text-3xl font-bold text-gray-800">{{ title }}</h1>
  
          <!-- Article Description -->
          <p class="mt-4 text-gray-600">{{ description }}</p> <br>
          <p class="mt-4 text-gray-600">{{ description }}</p> <br>
          <p class="mt-4 text-gray-600">{{ description }}</p> <br>
          <p class="mt-4 text-gray-600">{{ description }}</p> <br>
          <p class="mt-4 text-gray-600">{{ description }}</p> <br>
          <p class="mt-4 text-gray-600">{{ description }}</p> <br>
          <p class="mt-4 text-gray-600">{{ description }}</p> <br>
          <p class="mt-4 text-gray-600">{{ description }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
    
      title: {
        type: String,
        required: true,
        default: 'Title is empty'
      },
      
      description: {
        type: String,
        required: true,
        default: 'Body is empty'
      }
    }
  };
  </script>
  
  <style>
  /* Add any custom styles here */
  </style>
  