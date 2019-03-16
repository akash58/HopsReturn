<template>
  <div>
    <v-navigation-drawer
      id="appDrawer"
      :clipped="clipped"
      v-model="drawer"
      enable-resize-watcher
      app
      class="pa-0"
    >
      <v-toolbar flat dense>
        <v-list>
          <v-list-tile>
            <v-list-tile-title class="title">
              HOPS
            </v-list-tile-title>
          </v-list-tile>
        </v-list>
      </v-toolbar>
      <v-divider/>
      <no-ssr>
        <v-list>
          <v-list-group prepend-icon="supervisor_account">
            <v-list-tile slot="activator">
              <v-list-tile-content>
                <v-list-tile-title class="black--text font-weight-regular">Admin</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Page Management
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Roles
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Manage Users
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Create Company
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
          </v-list-group>
          <v-list-group prepend-icon="create_new_folder">
            <v-list-tile slot="activator">
              <v-list-tile-content>
                <v-list-tile-title class="black--text font-weight-regular">Configuration</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Attendant
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Categories
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Customers
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Foods
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Food Components
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Packages
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Payment Modes
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Suppliers
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  System Parameter
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Tables
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Units
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
          </v-list-group>
          <v-list-group prepend-icon="games">
            <v-list-tile slot="activator">
              <v-list-tile-content>
                <v-list-tile-title class="black--text font-weight-regular">Games</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Game Types
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Games
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Serials
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
          </v-list-group>
          <v-list-group prepend-icon="fastfood">
            <v-list-tile slot="activator">
              <v-list-tile-content>
                <v-list-tile-title class="black--text font-weight-regular">Food Operations</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Food Operations
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Purchase orders
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Stock Audit
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Food Expiry
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
          </v-list-group>
          <v-list-group prepend-icon="settings_overscan">
            <v-list-tile slot="activator">
              <v-list-tile-content>
                <v-list-tile-title class="black--text font-weight-regular">Operations</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Operations Overview
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Table Details
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Payments
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Memberships
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
          </v-list-group>
          <v-list-group prepend-icon="pageview">
            <v-list-tile slot="activator">
              <v-list-tile-content>
                <v-list-tile-title class="black--text font-weight-regular">Reports</v-list-tile-title>
              </v-list-tile-content>
            </v-list-tile>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Total Revenue Reports
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Food Order Reports
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Food Consumption Reports
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
            <nuxt-link
              to=""
              class="tdn black--text">
              <v-list-tile v-ripple>
                <v-list-tile-title class="font-weight-regular pl55">
                  Bill Archive Reports
                </v-list-tile-title>
              </v-list-tile>
            </nuxt-link>
          </v-list-group>
          <v-divider class="grey lighten-2"/>
          <v-list-tile
            v-ripple
          >
            <v-list-tile-title class="black--text font-weight-regular">Feedback</v-list-tile-title>
          </v-list-tile>
          <nuxt-link
            to=""
            class="tdn black--text">
            <v-list-tile
              v-ripple
            >
              <v-list-tile-title class="black--text font-weight-regular">About</v-list-tile-title>
            </v-list-tile>
          </nuxt-link>
        </v-list>
      </no-ssr>
    </v-navigation-drawer>
  </div>
</template>
<script>
export default {
  data  () {
    return {
      clipped: false,
      drawer: false,
      fixed: false
    }
  },
  created () {
    this.$nuxt.$on('APP_DRAWER_TOGGLED', () => {
      this.drawer = !this.drawer
    })
  },
  methods: {
  }
}
</script>

<style scoped>
.v-list{
  padding: 0px 0 8px;
}
.pl55 {
  padding-left: 55px;
}
</style>
