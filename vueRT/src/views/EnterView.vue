<script >
export default{
    data(){
        return {
            loginE:false,
            allIn:[],
            loginT:false,
            currentAcc:'',
            loginAcc:'',
            loginPass:'',
            regisE:false,
            regisMap:new Map(),
            regisAcc:'',
            regisPass:'',
            message:"",
            uniObj:"",
          }
    },
    methods: {
    addToMap() {
      if (this.regisAcc && this.regisPass&&!this.regisMap.has(this.regisAcc)) {
        this.allIn.push(this.regisAcc);
        this.regisMap.set(this.regisAcc, this.regisPass);
        //console.log(this.regisAcc);
        this.regisAcc = '';
        this.regisPass = '';
        this.regisE=false;
        
        alert('register complete!');
      }else {
        this.regisE=true;
      }
    },
    removeFromMap() {
      if (this.regisAcc&& this.regisPass&&this.regisMap.has(this.regisAcc)&&this.regisMap.get(this.regisAcc)==this.regisPass  ){
        this.allIn = this.allIn.filter(item => item !== this.regisAcc);
      this.regisMap.delete(this.regisAcc);
        //console.log(this.regisAcc);
        this.regisAcc = '';
        this.regisPass = '';
        this.regisE=false;
        

      }else {
        this.regisE=true;
      }
    },
    login(){
        if (this.loginAcc&& this.loginPass&&this.regisMap.has(this.loginAcc)&&this.regisMap.get(this.loginAcc)==this.loginPass &&this.loginT==false ){
            this.loginT=true;
            this.currentAcc=this.loginAcc;
            this.loginAcc='';
            this.loginPass='';
            this.loginE=false;
        }else
        {
          this.loginE=true;
        }
    },
    logout(){
        if(this.loginT==true){
            this.loginT=false;
            this.currentAcc='';
            this.loginAcc='';
            this.loginPass='';
            this.loginE=false;
        }else{
          this.loginE=true;
        }
    }
}
}
</script>

<template>
  <main>
    <h1>This is a form</h1>
    <h2>Fly to the universe</h2>
    <div class="form">
        <div class="register">
            
            <p>REGISTER</p>
            <fieldset>
            <label for="regisAcc">Account</label>
            <input v-model="regisAcc" placeholder="your account"  required type="text" id="regisAcc"/><br>
            <label for="regisPass">Password</label>
            <input v-model="regisPass" placeholder="your password" required type="password" id="regisPass"/><br>
            <p v-if="regisE" style="color:red">wrong information<br></p>
            <button @click="addToMap">register</button>
            <button @click="removeFromMap">destroy</button>
            </fieldset>
           </div>

            <div class="login">
            
            <p>LOGIN</p>
            <fieldset>
            <label for="loginAcc">Login</label>
            <input v-model="loginAcc" placeholder="your account"  required type="text" id="loginAcc"/><br>
            <label for="loginPass">Password</label>
            <input v-model="loginPass" placeholder="your password" required type="password" id="loginPass"/><br>
            <p v-if="loginE" style="color:red">ERROR!</p>
            <button @click="login">login</button>
            <button @click="logout">logout</button>
            
            </fieldset>

             </div>
    </div>
    <br>
    <div class="welcome" v-if="loginT">welcome!{{ currentAcc }}</div>
    <div class="accList">
        <ol>
            <li v-for="(item,index) in allIn">{{ item }}</li>
        </ol>
    </div>
    <footer class="prod">produced by @WYZ</footer>

  </main>
</template>

<style scoped>
.form{
    max-width: 400px;;
}
.welcome{
    position:absolute;
    top:100px;
    left:600px;
}
</style>
