<template>
  <div class="container container-products">
    <h1 class="title-products">Products by Categories</h1>
    <!------------------------- CATEGORY LIST ------------------------------>
    <div class="row">
        <div v-for="category in ProductsDB.categories" v-bind:key="category.id" @click="Category_Selected(category.id)" class="div-photo-subcat col-xs-3">
          <img :src="category.image" :title="category.name" class="img-thumbnail image-Show">
          <div class="middle-subcat">
              <div class="text">{{ category.name }}</div>
          </div>
        </div>
    </div>
    <hr>

    <!------------------------- PRODUCTS LIST ----------------------------->
    <div class="row">
        <div v-for="(product, index) in category_clicked" v-bind:key="product.id" @click="IndexSelected(index)" class="div-photo-carr col-sm-2 col-xs-4">
          <img :src="product.image" :title="product.name" class="img-thumbnail image-Show" data-toggle="modal" data-target="#myModal">
        </div>
    </div>

  <!------------------------- MODAL new Component ------------------------>
  <!-- The Modal -->
  <div class="modal fade" id="myModal">
    <div class="modal-dialog">
      <div class="modal-content">
      
        <!--------- Modal Header ---------->
        <div class="modal-header">
          <button type="button" class="close" data-dismiss="modal">&times;</button>
        </div>
        
        <!---------- Modal body ----------->
        <div class="modal-body">
          <!-- [carousel] -->
          <div class="row">
            
            <div class="col-xs-1">
              <i class="fa fa-arrow-left carousel-arrow arrow-left" @click="turnLeft()"></i>
            </div>
             <div class="col-xs-10">
              <img :src="category_clicked[indexSelected].image" :title="category_clicked[indexSelected].name" class="img-thumbnail image-modal">
            </div>
             <div class="col-xs-1">
              <i class="fa fa-arrow-right carousel-arrow arrow-right" @click="turnRight()"></i>
            </div>
          </div>

          <hr/>

          <!-- [Description] -->
          <div class="description-jewel">
            <div>
              <h2><b>{{ category_clicked[indexSelected].name }}</b></h2>
              <p class="description">{{ category_clicked[indexSelected].description }}</p>
            </div>
            <!-- [technical list] -->
            <ul>
              <li class="TL-unit"><b>Metal: </b>{{ category_clicked[indexSelected].metal }}</li>
              <li class="TL-unit"><b>Wheight: </b>{{ category_clicked[indexSelected].wheight }}</li>
              <li class="TL-unit"><b>Size: </b>{{ category_clicked[indexSelected].size }}</li>
            </ul>
          </div>
          
        </div>
          
        <!---------- Modal footer ---------->
        <div class="modal-footer">
          <button type="button" class="btn btn-danger" data-dismiss="modal">Close</button>
        </div>
        
      </div>
    </div>
  </div>
  <!-- --------====-------- -->

  </div>
</template>

<script>
export default {
  props:{
      // ALL JSON ( PRODUCTS AND CATEGORY - DB)
      ProductsDB: Object
      //--------------------------------------
  },
  data(){
    return{
      // All Products FILTER
      category_clicked: this.ProductsDB.products,

      indexSelected: 0 //product i selected to open modal 
    }
  },

  methods:{
    // CLIKED SUBCATEGORY TO INSERT ALL OBJ IN A ARRAY ----PRODUCTS----
    Category_Selected(id){
      // reset select of products
      this.indexSelected = 0

      // do the [filter]---
      if(id == -1) this.category_clicked = this.ProductsDB.products 
      else{
        this.category_clicked = []
        this.ProductsDB.products.forEach(element => {
          if(element.category_id == id) this.category_clicked.push(element) 
        });
      }
    },

    // ----[MODAL]----
    IndexSelected(index){ //product i selected to open modal 
      return this.indexSelected = index
    },
    turnLeft(){
      if(this.indexSelected == 0) return this.indexSelected = this.category_clicked.length -1
      else return this.indexSelected -= 1    
    },
    turnRight(){
      return (this.indexSelected == this.category_clicked.length -1) ? this.indexSelected = 0 : this.indexSelected += 1
    }
  }
}
</script>

<style>
  /* [Bring fonts] */
  @font-face {
    font-family: Santral;
    src: url(../assets/font/Santral-Light.otf);
  }
  .container-products{
    padding-top:80px;
    padding-bottom:100px;
  }
  .title-products{
    font-family: "Santral";
    text-align: center;
    margin-bottom: 50px;
  }
  /* ----------- [Category LIST] ---------- */
  .div-photo-subcat{
      position: relative;
  }
  .image-Show{
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
    -webkit-transition: all 0.6s cubic-bezier(0.165, 0.84, 0.44, 1);
    transition: all 0.6s cubic-bezier(0.165, 0.84, 0.44, 1);
    cursor: pointer;
  }

  .image-Show:hover {
    -webkit-transform: scale(1.1, 1.1);
    transform: scale(1.1, 1.1);
  }


  /* transparent, gonna show after hover  */
  .middle-subcat {
    transition: .5s ease;
    opacity: 0;
    position: absolute;
    top: 90%;
    left: 50%;
    transform: translate(-50%, -50%);
    -ms-transform: translate(-50%, -50%);
    text-align: center;
  }

  .div-photo-subcat:hover .middle-subcat {
    opacity: 1;
  }

  .div-photo-subcat:hover .image-Show {
    opacity: 0.6;
  }

  /* ----------- [PRODUCT LIST] ---------- */
  .div-photo-carr{
      margin-bottom: 25px;
  }

  /* =========[MODAL]========= */

  .image-modal{
    width: 90%;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
    max-width: 404px;
    max-height: 404px;
  }

  /* [ARROW] */
  .carousel-arrow{ 
    vertical-align: middle;
    height: 378px;
    padding: 0px;
    writing-mode: vertical-lr;
    font-size: xx-large;
    transform: scale(1);
    animation: pulse 2s infinite;
  }
  /* animation arrow */
  @keyframes pulse {
    0% {transform: scale(0.80);}
    70% {transform: scale(1);}
    100% {transform: scale(0.80);}
  }

  /* [DESCRIPTION] */
  .description-jewel{
    font-family: "Santral";
    text-align: left;
    margin-left: 50px;
    margin-right: 150px;
  }

  .description{
    text-align: justify;
    text-justify: inter-word;
  }
  /* =========[END MODAL]========= */

</style>