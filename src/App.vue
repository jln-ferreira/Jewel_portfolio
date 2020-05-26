<template>
  <div id="app">
    <Header />

    <div class="container">
      <Subcategory />
      <Carousel />
    </div>

  </div>
</template>

<script>
import Header from './components/header.vue'
import Subcategory from './components/subcategory.vue'
import Carousel from './components/carousel.vue'

export default {
  name: "App",
  components: {
    Header,
    Carousel,
    Subcategory
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
