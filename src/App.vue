<template>
  <div id="app">
    <Header />

    <div class="container">
      <Subcategory/>
      <Carousel />
    </div>

  <Footer />
  </div>
</template>

<script>
import Header from './components/header.vue'
import Subcategory from './components/subcategory.vue'
import Carousel from './components/carousel.vue'
import Footer from './components/footer.vue'

export default {
  name: "App",
  components: {
    Header,
    Carousel,
    Subcategory,
    Footer
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
