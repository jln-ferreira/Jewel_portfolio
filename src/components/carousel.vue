<template>
  <div class="container">
    <div class="row">
        <div v-for="(product, index) in ProductsDB.products" v-bind:key="product.id" @click="IndexSelected(index)" class="div-photo-carr col-sm-2 col-xs-4">
          <img :src="product.image" :title="product.name" class="img-thumbnail image-carr" data-toggle="modal" data-target="#myModal">
        </div>
    </div>

  <!-- MODAL new Component -->
  <Modal :ProductsDB="ProductsDB" :indexSelected="indexSelected" />
  <!-- --------====-------- -->

  </div>
</template>

<script>
// import components
import Modal from './modal_products.vue'

export default {
  components: {
    Modal
  },
    data(){
        return{
          indexSelected: 0
        }
      },
      props: {
        ProductsDB: Object
      },
      methods:{
        IndexSelected(index){
          return this.indexSelected = index
        }
    }
}
</script>

<style>
.div-photo-carr{
    margin-bottom: 25px;
}

.image-carr{
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
    -webkit-transition: all 0.6s cubic-bezier(0.165, 0.84, 0.44, 1);
    transition: all 0.6s cubic-bezier(0.165, 0.84, 0.44, 1);
    cursor: pointer;
}

.image-carr:hover {
  -webkit-transform: scale(1.25, 1.25);
  transform: scale(1.25, 1.25);
}


</style>