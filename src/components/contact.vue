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
                                <select v-model='country' class="form-control col-lg-2" id="country">
                                    <option selected>Choose...</option>
                                    <option value="1">Canada</option>
                                    <option value="2">Brazil</option>
                                    <option value="3">United States</option>
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
                            <button class="button btn-form"><span>Send</span></button>
                        </div>
                    </form>
                </div>
                <img src="images/contact/model_jewel.jpg" class="col-sm-6 contact-image">
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
    cursor: pointer;
}

.button span {
    cursor: pointer;
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


</style>