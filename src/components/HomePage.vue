<template>
  <div class="home-page">
    <div id="card">
      <img id="company-img" src="../../src/assets/gregoryFunding.png" alt="">
      <PlaceHolder :placeholders="placeholders"/>
      <div class="reg-detail">
        <div class="pw-q-div">
           <a class="pw">Forgot password?</a><a class="security-q">ForgotSecurity question/answer?</a>
        </div>
        <a class="change-q">
           Change security question/answer?
        </a>
      </div>
      <div id="login">Login</div>
      <div class="reg-detail pw-q-div bottom-reg">
        <a>Register</a><a>Contact Us</a>
      </div>
    </div>
  </div>
</template>

<script>
import PlaceHolder from './PlaceHolder'

export default {
  props: {
    msg: String
  },
  components:{
    PlaceHolder
  },
  data() {
   return {
      placeholders:[
        {
          "title":"Email",
          "content":""
        },
        {
          "title":"Password",
          "content":""
        },
        {
          "title":"Select Security Question",
          "content":""
        },
        {
          "title":"Answer",
          "content":""
        }
     ]
  }
 }
}
</script>

<style scoped>
  .home-page{
    width:20%;
    margin: auto;
    font-size:14px;
    font-family: -apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,sans-serif;
    font-weight: 100;
  }
  #card{
    border: 1px solid rgba(0,0,0,0.125);
    padding: 25px 0;
  }

  #company-img{
    width: 90%;
  }

  #login{
    width: 86%;
    margin: auto;
    padding: 8px 8px;
    border: 1px solid #B47804;
    background: #B47804;
    color: white;
  }

  #login:hover{
      color:#B47804;
      background: white;
      cursor: pointer;
    }

.reg-detail{
     color:#B47804;
     padding: 15px 0;
  }
.pw-q-div{
    display:flex;
    justify-content: space-between;
    width: 89%;
    margin: auto;
}
.change-q{
    display: flex;
    justify-content: flex-end;
    margin: 12px 21px;
}
.bottom-reg{
    padding-top: 55px;
}
a:hover{
    text-decoration: underline;
    cursor: pointer;
}
</style>
