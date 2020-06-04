<template>
  <div class="container-fluid">
    <div class="row">
      <!-- [foto Model] -->
      <div class="col-sm-6 col-image">
          <img class="img-responsive" src="images/topMind/topMind_Model.JPG">
      </div>
      <!-- [foto Jewel] -->
      <div class="col-sm-6 col-image">
        <img class="img-responsive" src="images/topMind/topMind_Jewel.JPG" >
      </div>
    </div>

      <div class="row">
        <div class="meet-company">
          <h3>Our Goldhouse</h3>
          <p>Where these unparalleled sweets are made.</p>
        </div>
      </div>

  </div>
</template>

<script>
export default {

}
</script>

<style>
  .col-image{
    padding: 0px;
  } 
  
  .meet-company{
    font-family: "Santral";
    display: inline-block;
    border: outset;
    padding: 10px 30px;
    margin-top: 20px;
    cursor: pointer;
    transition: 0.5s;
  } 
  .meet-company:hover{
-webkit-box-shadow: 0px 0px 34px -11px rgba(0,0,0,0.75);
-moz-box-shadow: 0px 0px 34px -11px rgba(0,0,0,0.75);
box-shadow: 0px 0px 34px -11px rgba(0,0,0,0.75);
  } 

</style>