<script setup>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <Header></Header>
  <Main></Main>
  <Footer></Footer>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Poppins", sans-serif;
  line-height: 1.6;
  color: #333;
  background-color: #f9f9f9;
}

@media (max-width: 768px) {
  .search-bar input {
    width: 100%;
  }

  ul li {
    display: block;
    margin: 10px 0;
  }
}
</style>
