<template>
  <div class="row">
      <div v-for="category in categories" v-bind:key="category.id" class="div-photo col-sm-4">
        <img :src="category.image" :title="category.name" class="img-thumbnail image">
        <div class="middle">
            <div class="text">{{ category.name }}</div>
        </div>
      </div>
  </div>

</template>

<script>
export default {
    data(){
        return{
            categories:[
                {   //chains
                    id:1,
                    name:'Chains',
                    image:'/img/chains.729e8290.jpg'
                },
                {   //Earrings
                    id:2,
                    name:'Earrings',
                    image:'/img/earrings.28882618.jpg'
                },
                {   //Necklaces
                    id:3,
                    name:'Necklaces',
                    image:'/img/necklaces.4c655fe9.jpg'
                }

            ]
        }
    },
    methods:{
        
    }
}
</script>

<style>
.div-photo{
    position: relative;
}

.image{
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
    -webkit-transition: all 0.6s cubic-bezier(0.165, 0.84, 0.44, 1);
    transition: all 0.6s cubic-bezier(0.165, 0.84, 0.44, 1);
}

.image:hover {
  -webkit-transform: scale(1.1, 1.1);
  transform: scale(1.1, 1.1);
}


/* transparent, gonna show after hover  */
.middle {
  transition: .5s ease;
  opacity: 0;
  position: absolute;
  top: 90%;
  left: 50%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  text-align: center;
}

.div-photo:hover .middle {
  opacity: 1;
}

.div-photo:hover .image {
  opacity: 0.6;
}

</style>