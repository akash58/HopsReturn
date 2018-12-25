<template>
  <div>
    <v-layout row wrap>
      <v-flex xs6 class="" >
        <v-card class="elevation-0 login-bg" :style="{ backgroundImage: `url(${backgroundUrl})` }">
          <!-- <div > -->
            <v-content class="layer white--text px-5">
              <v-container class="my-5">
                <div class="subheading">HOPS is stands for Hospitality Operations.</div>
                <ul>
                  <li class="py-1">Inventory Management.</li>
                  <li class="py-1">Food Supply Management.</li>
                  <li class="py-1">Order Management.</li>
                  <li class="py-1">Table Management.</li>
                  <li class="py-1">Delivery  Management.</li>
                  <li class="py-1">Stock Management.</li>
                  <li class="py-1">Game Management.</li>
                  <li class="py-1">Print Bills/Receipts.</li>
                </ul>
              </v-container>
            </v-content>
          <!-- </div> -->
        </v-card>
      </v-flex>
      <v-flex xs6 class="">
        <v-card class="elevation-0 px-5" height="560px">
          <v-content class="px-5">
            <!-- <v-container> -->
              <v-card-text>
                <div class="layout column align-center my-5">
                  <h1 class="flex black--text">LOGIN</h1>
                  <h4 class="grey--text body-2 mt-1">Welcome back! Please login to your account</h4>
                </div>                
                <v-form>
                  <v-text-field append-icon="person" name="login" label="UserName/Email" type="text" v-model="model.username"></v-text-field>
                  <v-text-field append-icon="lock" name="password" label="Password" id="password" type="password" v-model="model.password"></v-text-field>
                </v-form>
                <div class="body-1" align="center">Forgot Password?</div>
              </v-card-text>
              <v-card-actions class="mt-1">
                <v-btn block color="primary" @click="login" :loading="loadingLogin">Login</v-btn>
                <v-spacer></v-spacer>
                <v-btn block color="white" @click="signup" :loading="loadingSignup">Signup</v-btn>
              </v-card-actions>
            <!-- </v-container> -->
          </v-content>
        </v-card>
      </v-flex>
    </v-layout>
  </div>
</template>

<script type="text/javascript">
  export default {
    data () {
      return {
        loadingLogin: false,
        loadingSignup: false,
        model: {
          username: 'admin@isockde.com',
          password: 'password'
        },
        backgroundUrl: require('~/static/authentication/authentication_msite.png')
      }
    },
    methods: {
      login () {
        this.loadingLogin = true
        setTimeout(() => {
          this.$router.push('/')
        }, 1000)
      },
      signup () {
        this.loadingSignup = true
        setTimeout(() => {
          this.$router.push('/signup')
        }, 1000)
      }
    }
  }
</script>

<style scoped>
.login-bg {
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;
  /*width: 100%;*/
  height: 100%;
}
.layer {
  background-color: rgba(2,136,209, 0.5);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
#login {
    height: 50%;
    width: 100%;
    position: absolute;
    top: 0;
    left: 0;
    content: "";
    z-index: 0;
  }
</style>