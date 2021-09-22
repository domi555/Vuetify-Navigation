<template>
  <v-app>
    <v-app-bar class="grey lighten-5" height="74" app>
      <img
        class="mx-2"
        src="images/fearlessfido-logo.svg"
        style="height:150px; margin-top:100px"
      />
      <span
        class="text-truncate text-h4 blue-grey--text darken-1"
        style="font-family: Poppins"
        >A Dog With a Mission</span
      >
      <v-spacer></v-spacer>
      <div class="hidden-sm-and-down">
        <v-btn active-class="amber darken-2" class="custom-bg" to="/" exact
          >Home</v-btn
        >
        <v-btn
          active-class="amber darken-2"
          class="ml-5 custom-bg"
          to="/products"
          exact
          >Products</v-btn
        >
        <v-btn
          active-class="amber darken-2"
          class="ml-5 custom-bg"
          to="/about"
          exact
          >About</v-btn
        >
      </div>

      <v-app-bar-nav-icon
        @click.stop="drawer = !drawer"
        class="hidden-md-and-up grey darken-3 white--text"
      ></v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer
      class="hidden-md-and-up"
      app
      hide-overlay
      disable-resize-watcher
      v-model="drawer"
      right
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Menu
          </v-list-item-title>
          <v-list-item-subtitle>
            Please select
          </v-list-item-subtitle>
        </v-list-item-content>
        <v-btn text @click="drawer = false" class="grey darken-3 white--text">
          <v-icon>mdi-close</v-icon>
        </v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list-item-group>
        <v-list-item
          active-class="amber darken-2 white--text"
          link
          v-for="(route, i) of routes"
          :key="i"
          :to="route.to"
        >
          {{ route.name }}
        </v-list-item>
      </v-list-item-group>
    </v-navigation-drawer>

    <v-main>
      <div class="d-flex">
        <div style="width:250px"></div>
        <div class="mt-10" style="flex:1">
          <router-view></router-view>
        </div>
      </div>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    routes: [
      { name: 'Home', to: '/' },
      { name: 'Products', to: '/products' },
      { name: 'About', to: '/about' },
    ],
    drawer: false,
  }),
};
</script>

<style scoped>
.custom-bg:not(active-class) {
  color: #ffffff !important;
  background-color: #333333 !important;
}
</style>
