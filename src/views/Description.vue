<template>
    <div class="description">
      <h2>{{ title }}</h2>
      <p>{{ content }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: String,
      content: String
    }
  };
  </script>
  