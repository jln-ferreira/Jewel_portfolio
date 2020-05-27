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

            <!-- ---- [ Social Media ] ---- -->
            <div class="row social-Media"> 
                <hr>

                <!-- [social media] -->
                <div class="social-buttons">
                    <a href="#"><i class="fa fa-facebook"></i></a>
                    <a href="#"><i class="fa fa-instagram"></i></a>
                    <a href="#"><i class="fa fa-youtube"></i></a>
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
    @font-face {
    font-family: MaisonNeue;
    src: url(../assets/font/MaisonNeue-Bold.ttf);
    }
    
    .footer{
        background-color: black;
    }

    /* ------[Localizations]----- */
    .row-location{
        margin-top: 20px;
        margin-bottom: 25px;
    }
    .social-Media{
        margin-bottom: 35px;
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
    /* [end localization] */

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

    .social-buttons a:hover .fa-facebook{
        color: #4267B2;
    }
    .social-buttons a:hover .fa-instagram{
        color: #E1306C;
    }
    .social-buttons a:hover .fa-youtube{
        color: #FF0000;
    }
    


</style>