<template>
  <v-app>
    <v-app-bar class="blue" app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="white--text"></v-app-bar-nav-icon>
      <span class="white--text title">Layout Demo</span>
    </v-app-bar>
    <v-navigation-drawer app hide-overlay disable-resize-watcher v-model="drawer">
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

      <v-list>
        <v-list-item-group>
          <v-list-item active-class="blue white--text" link v-for="(route, i) in routes" :key="i" :to="route.link">
            <v-list-item-content>
              <v-list-item-title v-text="route.name"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-main class="ma-2">
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    drawer: true,
    routes: [
      { name: 'Home', link: '/' },
      { name: 'Products', link: 'products' },
      { name: 'Team', link: 'team' },
      { name: 'About', link: 'about' },
    ],
  }),
};
</script>
