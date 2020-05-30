<template>
  <div class="container">
    <div class="row">
        <div v-for="category in ProductsDB.categories" v-bind:key="category.id" @click="subSelect(category.id)" class="div-photo-subcat col-sm-4">
          <img :src="category.image" :title="category.name" class="img-thumbnail image-subcat">
          <div class="middle-subcat">
              <div class="text">{{ category.name }}</div>
          </div>
        </div>
    </div>
    <hr>
  </div>
</template>

<script>
export default {
    data(){
        return{

        }
    },
    props: {
      ProductsDB: Object
    },
    methods:{
      subSelect(id){
        return console.log(id)
      }
        
    }
}
</script>

<style>

.div-photo-subcat{
    position: relative;
}

.image-subcat{
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
    -webkit-transition: all 0.6s cubic-bezier(0.165, 0.84, 0.44, 1);
    transition: all 0.6s cubic-bezier(0.165, 0.84, 0.44, 1);
    cursor: pointer;
}

.image-subcat:hover {
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

.div-photo-subcat:hover .image-subcat {
  opacity: 0.6;
}

</style>