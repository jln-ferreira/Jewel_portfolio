<template>
  <div class="container">
    <div class="row">
        <div v-for="product in category_clicked" v-bind:key="product.id" @click="IndexSelected(product.id)" class="div-photo-carr col-sm-2 col-xs-4">
          <img :src="product.image" :title="product.name" class="img-thumbnail image-carr" data-toggle="modal" data-target="#myModal">
        </div>
    </div>

  <!-- MODAL new Component -->
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
  data(){
    return{
      indexSelected: 0,
      lengthProduct: this.category_clicked.length -1

    }
  },
  props: {
    category_clicked: Array
      
  },
  methods:{
    IndexSelected(id){
      return this.indexSelected = id
    },
    turnLeft(){
      return (this.indexSelected == 0) ? this.indexSelected = this.lengthProduct : this.indexSelected -= 1
    },
    turnRight(){
      return (this.indexSelected == this.lengthProduct) ? this.indexSelected = 0 : this.indexSelected += 1
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

  /* =========[MODAL]========= */
  /* [Bring fonts] */
  @font-face {
    font-family: Santral;
    src: url(../assets/font/Santral-Light.otf);
  }

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