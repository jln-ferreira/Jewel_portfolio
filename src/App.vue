<template>
  <div id="app">
    
    <Header />
    <TopMind />
    <AboutCompany />
    <Carousel :ProductsDB="myJson"/> 
    <Contact />
    <Footer />

  </div>
</template>

<script>
// import components
import Header from './components/header.vue'
import TopMind from './components/topMind.vue'
import AboutCompany from './components/aboutCompany.vue'
import Carousel from './components/carousel.vue'
import Contact from './components/contact.vue'
import Footer from './components/footer.vue'

// import json
import json from '../public/json/data.json';

export default {
  name: "App",
  components: {
    Header,
    TopMind,
    AboutCompany,
    Carousel,
    Contact,
    Footer
  },
  data(){
    return{
      myJson: json
    }
  },
  methods:{
    
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
