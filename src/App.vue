<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <nav>
      <RouterLink to="/home">Home</RouterLink>
      <RouterLink to="/">Form</RouterLink>
    </nav>
  </header>

  <main>
    <RouterView />
  </main>
</template>

<style>
header {
  background-color: #eee;
  width: 100%;
  text-align: center;
  padding: 10px;
}

header a {
  color: #444;
  padding: 10px;
  font-weight: bold;
  font-size: 20px;
}

main {
  width: 80%;
  height: 80vh;
  background-color: #eee;
  margin: 10px auto;
  display: flex;
  align-items: center;
  text-align: center;
  justify-content: center;
}

h1 {
  font-weight: bold;
  font-size: 25px;
  width: 100%;
}
</style>
