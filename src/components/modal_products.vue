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
              <div class="div-photo-Mod col-sm-12">
                <img :src="ProductsDB.products[indexSelected].image" title="image" class="img-thumbnail image-mod">
              </div>
          </div>

          <hr/>

          <!-- [Description] -->
          <div>
            
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
  .div-photo-Mod{
    
  }

.image-mod{
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
    max-width: 404px;
    max-height: 404px;
  }

</style>