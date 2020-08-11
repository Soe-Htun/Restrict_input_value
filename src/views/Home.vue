<template>
  <div class="cont">
   
    <div class="login">
     <h1>Restrict Input value</h1><br>
      <!-- <input id="name" v-model="name" @input="name=name.replace(/[0-9]/, '')" placeholder="EmailAddress" /><br> -->
      <input id="name" v-model="name" placeholder="EmailAddress" /><br>
      <input type="password" id="password" v-model="password" @input="password=password.replace(/[^a-z,A-Z]/g, '')" placeholder="Password(A-Z only)"/>
      <br />
      <span @click="show_hide()">
        <i v-if="hide" class="far fa-eye-slash"></i>
        <i v-if="show" class="fas fa-eye"></i>
      </span>
      <el-button id="btn" type="primary" @click="login">Login(Ent)</el-button>
      <el-button type="primary" @click="Clear()" id="sign">Clear(↑)</el-button>
    </div>

    <!-- <div class="dialog" v-if="dialog==1">
      <el-input id="regname" v-model="reg_name" placeholder="Email Address"></el-input>
      <el-input type="password" id="regpassword" v-model="reg_password" placeholder="Password"></el-input>
      <el-button id="signbtn" type="primary" @click="Signup_here">Sign_up</el-button>
      <el-button id="signcancel" @click="cancel()">Cancel(-)</el-button>
    </div> -->
  </div>
</template>

<script>
export default {
  name:'home',
  data() {
    return {
      hide:true,
      show:false,
      name:'',
      password:'',
    }
  },
  methods:{
    show_hide() {
      var pass = document.getElementById("password");
      if (pass.type == "password") {
        pass.type = "text";
        this.hide =false;
        this.show=true;
      } else {
        pass.type = "password";
        this.show=false;
        this.hide=true;
      }
    },
    Clear(){
      this.name='';
      this.password=''
    }


  },
  created(){
  }
}
</script>

<style>
h1{
  position: relative;
  text-shadow: 3px 3px grey;
}
.cont {
  position: fixed;
  width: 100%;
  height: 100%;
}
.login {
  position: absolute;
  top: 50%;
  left: 50%;
  margin: -250px 0px 0px -150px;
}
#name {
  text-indent: 10px;
  width: 220px;
  height: 40px;
  border-radius: 10px;
  border: 1px solid grey;
  outline: none;
  font-size: 20px;
}
#password {
  outline: none;
  margin: 25px 0px;
  text-indent: 10px;
  width: 220px;
  height: 40px;
  border-radius: 10px;
  border: 1px solid grey;
  font-size: 20px;
}
::placeholder{
  color: black;
  font-weight: 600;
  font-size: 16px;
}
#btn {
  margin-top:5px ;
  margin-left: 0px;
  width: 100px;
  height: 46px;
  border-radius: 10px;
}
#sign {
  margin-left: 25px;
  width: 100px;
  height: 46px;
  border-radius: 10px;
}
i {
  position: absolute;
  top: 42%;
  left: 79%;
}
</style>
