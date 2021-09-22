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
    </v-app-bar>

    <v-main>
      <div class="d-flex fill-height">
        <div class="d-flex align-center" style="width: 300px;">
          <div class="ml-2">
            <v-navigation-drawer
              style="border: 1px solid #333333;"
              permanent
              expand-on-hover
              disable-resize-watcher
            >
              <v-list>
                <v-list-item class="px-2">
                  <v-list-item-avatar>
                    <v-img src="/images/prof_baumgartner.png"></v-img>
                  </v-list-item-avatar>

                  <v-list-item-content>
                    <v-list-item-title
                      class="text-subtitle-1 font-weight-regular"
                    >
                      Your Trainer
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list>

              <v-divider></v-divider>

              <v-list-item-group>
                <v-list-item
                  active-class="amber darken-2 white--text"
                  link
                  v-for="(route, i) of routes"
                  :key="i"
                  :to="route.to"
                >
                  <v-list-item-icon>
                    <v-icon>{{ route.mdi }}</v-icon>
                  </v-list-item-icon>
                  <v-list-item-title>{{ route.name }}</v-list-item-title>
                </v-list-item>
              </v-list-item-group>
            </v-navigation-drawer>
          </div>
        </div>
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
      { name: 'Home', to: '/', mdi: 'mdi-account-plus' },
      { name: 'Products', to: '/products', mdi: 'mdi-account-group' },
      { name: 'About', to: '/about', mdi: 'mdi-information' },
    ],
  }),
};
</script>

<style scoped>
.custom-bg:not(active-class) {
  color: #ffffff !important;
  background-color: #333333 !important;
}
</style>
