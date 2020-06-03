<template>
  <div id="app">
    
    <Header />
    <Subcategory :ProductsDB="myJson" @Category_Selected="getCategory_Selected"/>
    <Carousel :category_clicked="this.category_clicked_json"/> 
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
      myJson: json,
      category_clicked_json: json.products
    }
  },
  methods:{
    // Filter when click subcategory
    getCategory_Selected(value){
      if(value == -1) this.category_clicked_json = this.json.products 
      else{
        this.category_clicked_json = []
        this.myJson.products.forEach(element => {
          if(element.category_id == value) this.category_clicked_json.push(element) 
        });
      }
    }//end filter category
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
