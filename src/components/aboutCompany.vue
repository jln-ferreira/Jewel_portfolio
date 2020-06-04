<template>
    <div>
        <div class="meet-company" data-toggle="modal" data-target="#AboutCompany">
            <h3>Our Goldhouse</h3>
            <p>Where these unparalleled sweets are made.</p>
        </div>

        <!------------------- The Modal --------------------->
        <div class="modal fade" id="AboutCompany">
            <div class="modal-dialog modal-lg">
                <div class="modal-content">
                    <!----------- Modal header ----------------->
                    <div class="modal-body">
                        <div class="about-header">
                           <h1><b>World of *JEWEL*</b></h1>
                           <div class="row about-header-whenStart">
                                <p>Where its began YYYY why grew @@@@@@@@@@@ Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum, architecto rem nemo perferendis quidem distinctio ut natus eveniet consequatur</p>
                            </div>
                        </div>
                        <!----------- Modal Body ----------------->
                        <div class="about-main">
                           <div class="about-session-heritage row">
                                <div class="col-sm-6">
                                    <p>Heritage..... Homero history @@@@@ Lorem ipsum dolor sit amet consectetur adipisicing elit. Nobis molestias sapiente doloribus explicabo! Adipisci, quisquam quia corrupti modi voluptate esse dolorum officia labore, sit velit iusto cum ab vero architecto?</p>
                                </div>
                                <div class="col-sm-6">
                                    <img src="images/topMind/topMind_Model.JPG" class="img-responsive">
                                </div> 
                            </div> 
                            <div class="about-session-whyUs row">
                                <div class="col-sm-12">
                                    <img src="images/topMind/topMind_Jewel.JPG" class="img-responsive">
                                    <p>Oferecemos um servico diferenciado de preco e todos os produtos vem com alguma coisa que faz voce ficar alucinado pelo produto</p>
                                </div>
                            </div> 
                            <div class="about-session-lastContent row">
                                <div class="col-sm-12">
                                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatum nisi iure distinctio esse in rem itaque nemo repudiandae illum? Architecto quidem nam et aliquam repudiandae corporis dignissimos quas, aliquid non.</p>
                                </div>
                            </div> 
                        </div>  
                    </div>
                    
                    <!-- Modal footer -->
                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                    </div>
                    
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {

}
</script>

<style>
/* [CLICK OPEN MODAL] */
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

/* [MODAL HERE!] */
    .modal{
        font-family: "Santral";
    }

    /* header modal */
    .about-header-whenStart{
        text-align: -webkit-center;
        padding-top: 14px;
        padding-bottom: 20px;
    }
    .about-header p{
        width: 50%;
        text-align: justify;
        text-justify: inter-word;
    }

    /* Body modal */
    /* heritage */
    .about-session-heritage p{
        text-align: justify;
        text-justify: inter-word;
    }

    /* why Us */
    .about-session-whyUs  img{
        position: relative;
    }
    .about-session-whyUs  p{
        position: absolute;
        bottom: 50%;
        left: 4%;
        max-width: 30%;
    }
    @media screen and (max-width: 768px) {
        .about-session-whyUs  img{
            position: static;
        }
        .about-session-whyUs  p{
            position: static;
            max-width: 100%;
        }
    }

    /* lastContent */
    .about-session-lastContent{
        text-align: -webkit-center;
        padding-top: 14px;
        padding-bottom: 20px;
    }
    .about-session-lastContent p{
        width: 50%;
        text-align: justify;
        text-justify: inter-word;   
    }
    @media screen and (max-width: 768px) {
        .about-session-lastContent p{
            width: 70%;
        }
    }
    
    


</style>