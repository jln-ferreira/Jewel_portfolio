<template>
  <div class="contact">
      <div class="container">
          <h3 class="contact-title col-sm-12">Contact Us</h3>
          <div class="contact-form col-sm-6">
                <form>
                    <div class="form-group row">
                        <label for="name" class="col-xs-3 col-form-label-sm label-form">Your name:</label>
                        <div class="col-xs-8">
                            <input type="text" class="form-control" id="name" placeholder="Mariana Dias">
                        </div>
                    </div>
                    <div class="form-group row">
                        <label for="email" class="col-xs-3 col-form-label label-form">Your e-mail:</label>
                        <div class="col-xs-8">
                            <input type="email" class="form-control" id="email" placeholder="john.doe@example.com">
                        </div>
                    </div>
                    <div class="form-group row">
                        <label class="col-xs-3 label-form" for="country">Country:</label>
                        <div class="col-xs-8">
                            <select class="form-control col-lg-2" id="country">
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
                            <textarea class="form-control" id="contact_text" rows="7"></textarea>
                        </div>
                    </div>
                    <div class="form-group row">
                        <button class="button btn-form"><span>Send</span></button>
                    </div>

                </form>
          </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.contact{
    background-color: rgb(209, 209, 209);
}
.contact-title{
    color:#ef0d33;
    font-size: 96px;
    font-weight: 300;
    margin: 50px;
    font-family: 'Trump Gothic East';
    letter-spacing: 0px;
    
}
.contact-form{
    background-color: white;
    padding: 17px 8px 29px 13px;
    border-radius: 17px;
    -webkit-box-shadow: 10px 7px 30px -12px rgba(0,0,0,0.45);
    -moz-box-shadow: 10px 7px 30px -12px rgba(0,0,0,0.45);
    box-shadow: 10px 7px 30px -12px rgba(0,0,0,0.45);
}

.label-form{
    text-align: -webkit-left;
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






</style>