<template>
  <div>
    <SideNav></SideNav>
    <v-toolbar fixed app dense color="blue" :clipped-left="clipped">
      <v-toolbar-side-icon
        class="white--text"
        @click.stop="drawerClick">
      </v-toolbar-side-icon>
      <nuxt-link to="/" class="tdn">
        <v-toolbar-title class="white--text" v-text="title"></v-toolbar-title>
      </nuxt-link>
      <v-spacer></v-spacer>
      <nuxt-link to="/login" class="tdn" v-if="this.$route.path !== `/login` && this.$route.path !== `/signup` ">
        <v-btn class="white--text subheading" flat>Login & Signup</v-btn>
      </nuxt-link>
    </v-toolbar>
  </div>
</template>

<script type="text/javascript">
export default {
  components: {
    SideNav: () => import('~/components/SideNav')
  },
  props: {
    title: {
      type: String,
      required: true,
      default: 'deals'
    }
  },
  data  () {
    return {
      clipped: false,
      drawer: true,
      ssr: true,
      e1: 1
    }
  },
  methods: {
    drawerClick () {
      this.$nuxt.$emit('APP_DRAWER_TOGGLED')
    }
  }
}
</script>

<style type="text/css" scoped>
.rimg {
  width: 37px;
}
.f18 {
  font-size: 18px;
}
</style>
