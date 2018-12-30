<template v-if="forgotPwdDialog">
  <v-dialog
    v-model="forgotPwdDialog"
    width="500"
  >
    <v-card>
    <v-form ref="forgotPwdForm" v-model="forgotPasswordValid">
      <v-layout row wrap class="mx-3">
        <div class="layout column align-center mt-4 mb-3">
          <h1 class="flex black--text">Forgot Password</h1>
          <h4 class="grey--text body-2 mt-1">Enter your email and we will send you the password reset link!</h4>
        </div> 
        <v-flex class="mt-2" xs12>
          <v-text-field
            v-model="forgotEmail"
            label="Please Enter your Email"
            prepend-icon="email"
            :rules="[(v) => !!v || 'Email is required' , (v) =>  v.length >= 3 || 'Email minimum 3 characters require', (v) => /.+@.+/.test(v) || 'E-mail must be valid']"
            autofocus
            required
          ></v-text-field>
        </v-flex>
      </v-layout>
      <div class="text-xs-right">
        <v-btn
          color="primary"
          flat
          :disabled="!forgotPasswordValid"
          class="font-weight-bold subheading"
          @click="forgotPwd"
        >
          SEND
        </v-btn>
      </div>
      </v-form>
    </v-card>
  </v-dialog>
</template>
<script type="text/javascript">
export default {
  data () {
    return {
      forgotPwdDialog: false,
      forgotEmail: '',
      forgotPasswordValid: true
    }
  },
  created () {
    this.$nuxt.$on('forgotPasswordClick', data => {
      this.forgotPwdDialog = data.forgotPwdDialog
    })
  },
  methods: {
    async forgotPwd () {
      const formData = new FormData()
      formData.append('email', this.forgotEmail)
      if (this.$refs.forgotPwdForm.validate()) {
        // .dispatch('me/FORGOT_PASSWORD', formData)
        // .then(res => {
        // this.$nuxt.$emit('snackbarError', {
        //   snackbar: true,
        //   message: 'Email Successfully Send',
        //   button: false
        // });
        this.$nuxt.$emit('forgotPasswordClick', { dialog: false },
          this.forgotEmail = '',
          this.forgotPwdDialog = false
        )
        // .catch(error => {
        // this.$store.commit('common/SET_LOADER');
        // this.showSnackBar = true;
        // this.$nuxt.$emit('snackbarError', {
        //   snackbar: this.showSnackBar,
        //   message: error.data.error,
        //   button: false
        // });
        // console.log(error)
        // });
      }
    }
  },
  watch: {
    forgotPwdDialog () {
      this.forgotEmail = ''
    }
  }
}
</script>
