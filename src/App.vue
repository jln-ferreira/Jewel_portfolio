<template>
  <div id="app">
    
    <Header />
    <Subcategory :ProductsDB="myJson"/>
    <Carousel :ProductsDB="myJson"/> 
    <Contact />
    <Footer />

  </div>
</template>

<script>
// import components
import Header from './components/header.vue'
import Subcategory from './components/subcategory.vue'
import Carousel from './components/carousel.vue'
import Contact from './components/contact.vue'
import Footer from './components/footer.vue'

// import json
import json from '../public/json/data.json';

export default {
  name: "App",
  components: {
    Header,
    Carousel,
    Subcategory,
    Contact,
    Footer
  },
  data(){
    return{
      myJson: json
    }
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
