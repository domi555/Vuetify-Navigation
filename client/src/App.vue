<template>
  <v-app>
    <!-- <v-navigation-drawer class="green" app>
      <span class="white--text title">v-navigation-drawer</span>
    </v-navigation-drawer>
    <v-app-bar class="yellow" app>
      <span class="title">v-app-bar</span>
    </v-app-bar>
    <v-main class="blue">
      <span class="white--text title">v-main</span>
    </v-main>
    <v-footer class="purple" app>
      <span class="white--text title mx-auto">v-footer</span>
    </v-footer>
    <v-bottom-navigation class="cyan" app>
      <span class="white--text title">v-bottom-navigation</span>
    </v-bottom-navigation> -->

    <!--(1)-->
    <!-- <v-system-bar class="pink" app>
      <span class="white--text title">v-system-bar</span>
    </v-system-bar> -->

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
      <v-btn active-class="amber darken-2" to="/" exact>Home</v-btn>
      <v-btn active-class="amber darken-2" to="/products" exact class="ml-5"
        >Products</v-btn
      >
      <v-btn active-class="amber darken-2" to="/about" exact class="ml-5">About</v-btn>
    </v-app-bar>
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
    //
  }),
};
</script>

<style scoped>
a:not(active-class) {
  color: #ffffff !important;
  background-color: #333333 !important;
}
</style>
