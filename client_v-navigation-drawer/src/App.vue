<template>
  <v-app>
    <v-app-bar class="blue" app>
      <v-app-bar-nav-icon
        @click.stop="drawer = !drawer"
        class="white--text"
      ></v-app-bar-nav-icon>
      <span class="white--text title">Layout Demo</span>
    </v-app-bar>

    <v-navigation-drawer
      app
      hide-overlay
      disable-resize-watcher
      v-model="drawer"
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
        <v-btn text @click="drawer = false">Close</v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list-item-group>
        <v-list-item
          active-class="blue lighten-2 white--text"
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
      <div class="ma-5">
        <router-view></router-view>
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
      { name: 'Team', to: '/team' },
      { name: 'About', to: '/about' },
    ],
    drawer: false,
  }),
};
</script>
