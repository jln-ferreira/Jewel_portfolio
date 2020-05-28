<template>
    <div class="contact">
        <div class="container">
            <h3 class="contact-title col-sm-12">Contact Us</h3>
            <div class="col-sm-12 contact-section">
                <div class="col-sm-6 contact-form">
                    <form>
                        <div class="form-group row">
                            <label for="name" class="col-xs-3 col-form-label-sm label-form">Your name:</label>
                            <div class="col-xs-8">
                                <input v-model='name' type="text" :class="['form-control', isNameValid()]" id="name" placeholder="Mariana Dias" required>
                            </div>
                        </div>
                        <div class="form-group row">
                            <label for="email" class="col-xs-3 col-form-label label-form">Your e-mail:</label>
                            <div class="col-xs-8">
                                <input v-model='email' type="email" :class="['form-control', isEmailValid()]" id="email" placeholder="mariana.dias@example.com" required>
                            </div>
                        </div>
                        <div class="form-group row">
                            <label class="col-xs-3 label-form" for="country">Country:</label>
                            <div class="col-xs-8">
                                <select v-model='country' :class="['form-control', 'col-lg-2', isCoutryValid()]" id="country">
                                    <option disabled value="">Please select one</option>
                                    <option value="Albania">Albania</option>                               
                                    <option value="Argentina">Argentina</option>
                                    <option value="Armenia">Armenia</option>
                                    <option value="Australia">Australia</option>
                                    <option value="Austria">Austria</option>
                                    <option value="Bahamas">Bahamas</option>
                                    <option value="Bangladesh">Bangladesh</option>
                                    <option value="Belgium">Belgium</option>
                                    <option value="Bermuda">Bermuda</option>
                                    <option value="Bolivia">Bolivia</option>
                                    <option value="Brazil">Brazil</option>
                                    <option value="Bulgaria">Bulgaria</option>
                                    <option value="Canada">Canada</option>
                                    <option value="Chile">Chile</option>
                                    <option value="China">China</option>
                                    <option value="Colombia">Colombia</option>
                                    <option value="Costa Rica">Costa Rica</option>
                                    <option value="Croatia">Croatia</option>
                                    <option value="Cuba">Cuba</option>
                                    <option value="Czech Republic">Czech Republic</option>
                                    <option value="Denmark">Denmark</option>
                                    <option value="Dominican Republic">Dominican Republic</option>
                                    <option value="East Timor">East Timor</option>
                                    <option value="Ecuador">Ecuador</option>
                                    <option value="El Salvador">El Salvador</option>
                                    <option value="France">France</option>
                                    <option value="French Guiana">French Guiana</option>
                                    <option value="Germany">Germany</option>
                                    <option value="Great Britain">Great Britain</option>
                                    <option value="Greece">Greece</option>
                                    <option value="Guatemala">Guatemala</option>                                    
                                    <option value="Hawaii">Hawaii</option>                                    
                                    <option value="Hong Kong">Hong Kong</option>
                                    <option value="Hungary">Hungary</option>                                    
                                    <option value="India">India</option>
                                    <option value="Iran">Iran</option>                                  
                                    <option value="Ireland">Ireland</option>                                   
                                    <option value="Italy">Italy</option>                                   
                                    <option value="Japan">Japan</option>                                                                       
                                    <option value="Korea South">Korea South</option>                                    
                                    <option value="Mexico">Mexico</option>                                    
                                    <option value="Morocco">Morocco</option> 
                                    <option value="New Zealand">New Zealand</option>
                                    <option value="Nicaragua">Nicaragua</option>                                    
                                    <option value="Panama">Panama</option>
                                    <option value="Paraguay">Paraguay</option>
                                    <option value="Peru">Peru</option>                        
                                    <option value="Portugal">Portugal</option>
                                    <option value="Puerto Rico">Puerto Rico</option>                                   
                                    <option value="Russia">Russia</option>                                   
                                    <option value="Saudi Arabia">Saudi Arabia</option>                                    
                                    <option value="Singapore">Singapore</option>
                                    <option value="Slovakia">Slovakia</option>
                                    <option value="Slovenia">Slovenia</option>
                                    <option value="South Africa">South Africa</option>
                                    <option value="Spain">Spain</option>
                                    <option value="Swaziland">Swaziland</option>
                                    <option value="Sweden">Sweden</option>
                                    <option value="Switzerland">Switzerland</option>
                                    <option value="Syria">Syria</option>
                                    <option value="Turkey">Turkey</option>
                                    <option value="United Kingdom">United Kingdom</option>
                                    <option value="Ukraine">Ukraine</option>
                                    <option value="United Arab Erimates">United Arab Emirates</option>
                                    <option value="United States of America">United States of America</option>
                                    <option value="Uraguay">Uruguay</option>
                                    <option value="Vatican City State">Vatican City State</option>
                                    <option value="Venezuela">Venezuela</option>
                                </select>
                            </div>
                        </div>
                        <div class="form-group row">
                            <label for="contact_text" class="col-xs-3 label-form">Message:</label>
                            <div class="col-xs-8">
                                <textarea v-model='message' class="form-control" id="contact_text" rows="7"></textarea>
                            </div>
                        </div>
                        <div class="form-group row">
                            <button :class="['button', 'btn-form', AllowSend()]"><span>Send</span></button>
                        </div>
                    </form>
                </div>
                <div class="col-sm-6 contact-image"></div>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    data(){
        return{
            name: "",
            email: "",
            country: "",
            message: "",
            regex_Email: /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/,
            regex_name: /^([A-Za-zéàë]{2,40} ?)+$/
        } 
    },
    methods: {
        isEmailValid() {
            return (this.email == "")? "" : (this.regex_Email.test(this.email)) ? 'has-success' : 'has-error';
        },
        isNameValid() {
            return (this.name == "")? "" : (this.regex_name.test(this.name)) ? 'has-success' : 'has-error';
        },
        isCoutryValid() {
            return (this.country != "")? 'has-success' : 'has-error';
        },
        AllowSend() {
            return (this.isEmailValid() == 'has-success' && this.isNameValid() == 'has-success' && this.isCoutryValid() == 'has-success') ? "" : 'block-send';
        }
    }
}
</script>

<style>
.contact{
    background-color: #ffe4e4;
}
.contact-title{
    color:#ef0d33;
    margin: 50px 0px 30px 0px;
    font-size: 96px;
    font-weight: 300;
    font-family: 'Trump Gothic East';
    letter-spacing: 0px;
    
}
.contact-section{
    margin-bottom: 25px;
    padding: 0px;
    border-radius: 10px;
    -webkit-box-shadow: 10px 7px 30px -12px rgba(0,0,0,0.45);
    -moz-box-shadow: 10px 7px 30px -12px rgba(0,0,0,0.45);
    box-shadow: 10px 7px 30px -12px rgba(0,0,0,0.45);
}
.contact-form{
    background-color: white;
    padding: 17px 8px 29px 13px;
    border-radius: 10px 0px 0px 10px;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}

.label-form{
    text-align: -webkit-left;
}

.contact-image{ 
    border-radius: 0px 10px 10px 0px;
    padding: 0;
    background-image: url('https://www.itl.cat/pngfile/big/88-887748_57-hd-jewelry-wallpapers-background-images-pile-of.jpg');
    background-position: center; /* Center the image */
    background-repeat: no-repeat; /* Do not repeat the image */
    background-size: cover;
    height: 417px;
}


/* [button form] */
.btn-form {
    width: 100px;
    height: 40px;
    border-radius: 4px;
    background-color:#ef0d33;
    border: none;
    color: #FFFFFF;
    font-size: 20px;
    transition: all 0.5s;
}

.button span {
    display: inline-block;
    position: relative;
    transition: 0.5s;
}

.btn-form span:after {
  content: '\00bb';
  position: absolute;
  opacity: 0;
  top: 0;
  right: -20px;
  transition: 0.5s;
}

.btn-form:hover span {
  padding-right: 25px;
}

.btn-form:hover span:after {
  opacity: 1;
  right: 0;
}

.block-send{
    opacity: 0.6;
    cursor: not-allowed;
    pointer-events: none;
    
}
/* END BUTTON FORM */

/* [VALIDATION FORM REGEX] */
.has-error{
    border: none;
    background-color: #fcdcdc;
    font-weight: bolder;
}
.has-success{
    border: none;
}
/* ======----======= */


@media screen and (max-width: 990px) {
  .contact-image {
    height: 439px;
  }
}

</style>