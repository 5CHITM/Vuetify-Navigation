<template>
  <v-app>
    <v-app-bar class="grey lighten-5" height="74" app>
      <img class="mx-2" src="images/fanta.svg" style="height:150px; margin-top:100px" />
      <span class="text-truncate text-h4 blue-grey--text darken-1" style="font-family: Poppins">Fancy Fanta</span>
      <v-spacer></v-spacer>

      <div v-show="$vuetify.breakpoint.lgAndUp">
        <v-btn active-class="orange" to="/" exact>Home</v-btn>
        <v-btn active-class="orange" to="/products" exact class="ml-5">Products</v-btn>
        <v-btn active-class="orange" to="/about" exact class="ml-5">About</v-btn>
      </div>

      <v-app-bar-nav-icon class="orange gray--text" @click="drawer = true" v-show="$vuetify.breakpoint.mdAndDown"></v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute right temporary disable-resize-watcher hide-overlay v-show="$vuetify.breakpoint.mdAndDown">
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Menu
          </v-list-item-title>
          <v-list-item-subtitle>
            Please select
          </v-list-item-subtitle>
        </v-list-item-content>
        <v-btn class="orange black--text" text @click="drawer = false">x</v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list>
        <v-list-item-group>
          <v-list-item active-class="orange black--text" link v-for="(route, i) in routes" :key="i" :to="route.link">
            <v-list-item-content>
              <v-list-item-title v-text="route.name"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <div class="d-flex">
        <div style="width:250px"></div>
        <div class="mt-10" style="flex:1"><router-view></router-view></div>
      </div>
    </v-main>

    <v-bottom-navigation>
      <v-btn to="/">
        <v-icon>mdi-home</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    drawer: false,
    routes: [
      { name: 'Home', link: '/' },
      { name: 'Products', link: 'products' },
      { name: 'Team', link: 'team' },
      { name: 'About', link: 'about' },
    ],
  }),
};
</script>
