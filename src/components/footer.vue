<template>
  <!-- Footer -->
    <div class="footer">
        <div class="container">

            <!-- ---- [ Localization ] ---- -->
            <div class="row row-location">
                <div class="col-sm-4">
                    <h1 class="place-XX">SP</h1>
                    <p class="place-Description">Beijamin Contant, São Paulo<br>BR 06475100</p>
                </div>
                <div class="col-sm-4">
                    <h1 class="place-XX">VAN</h1>
                    <p class="place-Description">West Keith rd, British Columbia<br>CA V7M1L5</p>
                </div>
                <div class="col-sm-4">
                    <h1 class="place-XX">PIT</h1>
                    <p class="place-Description">Algum lugar, Pennsylvania<br>USA XXXXX</p>
                </div>
            </div>

            <!-- ---- [ Contact info - Social Media ] ---- -->
            <div class="row">
                <!-- [Information] -->
                <div class="col-sm-6">

                </div>

                <div class="col-sm-2"></div>

                <div class="col-sm-4">
                    <hr>
                    <!-- [social media] -->
                    <div class="social-buttons">
                        <a href="#"><i class="fa fa-facebook"></i></a>
                        <a href="#"><i class="fa fa-instagram"></i></a>
                        <a href="#"><i class="fa fa-youtube"></i></a>
                    </div>
                    <!-- [Email] -->
                    <p class="test">jewel.jewel@jewel.je</p>

                </div>
            </div>


        </div>



    </div>

    
  <!-- Footer -->
</template>

<script>
export default {

}
</script>

<style>
    /* [Bring fonts] */
    @font-face {
    font-family: Trump Gothic East;
    src: url(../assets/font/trump_gothic_east_bold.ttf);
    }
    
    .footer{
        background-color: black;
    }
    .row-location{
        margin-top: 20px;
        margin-bottom: 70px;
    }
    .place-XX{
        color: white;
        font-size: 96px;
        font-weight: 300;
        font-family: 'Trump Gothic East';
        letter-spacing: 0px
    }
    .place-XX:hover{
        color: #ef0d33;
        transition-duration: 0.5s;
    }

    .place-Description{
        color: #888888;
        font-size: 18px;
        font-weight: 100;
        font-family: 'Maison Neue';
    }

    .place-XX:hover ~ .place-Description{
        color: rgb(190, 190, 190);
        transition-duration: 0.5s;
    }

    /* ---------[Media Icons]-------*/

    .social-buttons a{
        display: inline-flex;
        text-decoration: none;
        font-size: 30px;
        width: 60px;
        height: 60px;
        color: #fff;
        justify-content: center;
        align-items: center;
        position: relative;
        margin: 0 8px;
    }


    .social-buttons a i{
        transition: 0.3s ease-in;
    }

    .social-buttons a:hover .fa-facebook{
        background: linear-gradient(45deg,#7571b3,#2c1ace);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        transform: scale(1.7);
    }
    .social-buttons a:hover .fa-instagram{
        background: linear-gradient(45deg,#9c51ff,#d200da);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        transform: scale(1.7);
    }
    .social-buttons a:hover .fa-youtube{
        background: linear-gradient(45deg,#ff9393,#ff2542);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        transform: scale(1.7);
    }
    


</style>