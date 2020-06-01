<template>
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
              <i class="fa fa-arrow-left carousel-arrow arrow-left"></i>
            </div>
             <div class="col-xs-10">
              <img :src="ProductsDB.products[indexSelected].image" :title="ProductsDB.products[indexSelected].name" class="img-thumbnail image-modal">
            </div>
             <div class="col-xs-1">
              <i class="fa fa-arrow-right carousel-arrow arrow-right"></i>
            </div>
          </div>

          <hr/>

          <!-- [Description] -->
          <div class="description-jewel">
            <div>
              <h2><b>{{ ProductsDB.products[indexSelected].name }}</b></h2>
              <p class="description">{{ ProductsDB.products[indexSelected].description }}</p>
            </div>
            <!-- [technical list] -->
            <ul>
              <li class="TL-unit"><b>Metal: </b>{{ ProductsDB.products[indexSelected].metal }}</li>
              <li class="TL-unit"><b>Wheight: </b>{{ ProductsDB.products[indexSelected].wheight }}</li>
              <li class="TL-unit"><b>Size: </b>{{ ProductsDB.products[indexSelected].size }}</li>
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
</template>

<script>
export default {
  props: {
    ProductsDB: Object,
    indexSelected: Number
  }
}
</script>

<style>
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
    -webkit-writing-mode: vertical-lr;
    font-size: xx-large;
    transform: scale(1);
    animation: pulse 2s infinite;
  }
  /* animation arrow */
  @keyframes pulse {
	0% {
		transform: scale(0.80);
	}

	70% {
		transform: scale(1);
	}
	100% {
		transform: scale(0.80);
	}
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

</style>