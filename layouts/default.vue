<template>
  <v-app>
    <!-- <v-navigation-drawer
      :mini-variant.sync="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      fixed
      app
    >
      <no-ssr>
        <v-list>
          <nuxt-link to="/" class="tdn">
            <v-list-tile @click="">
              <v-list-tile-action>
                <v-icon color="grey darken-1" size="18" class="pl-1">local_activity</v-icon>
              </v-list-tile-action>
              <v-list-tile-content>
                <v-list-tile-title class="black--text font-weight-medium">Welcome HOPS</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
          </nuxt-link>
        </v-list>
      </no-ssr>
    </v-navigation-drawer> -->
    <Header :title="title"/>
    <v-content>
      <!-- <v-container> -->
        <nuxt />
      <!-- </v-container> -->
    </v-content>
    <v-footer class="text-xs-center" :fixed="fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        fixed: false,
        title: 'HOPS'
      }
    },
    components: {
      Header: () => import('~/components/MainHeader')
    }
  }
</script>
