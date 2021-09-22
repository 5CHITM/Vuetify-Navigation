<template>
  <v-app>
    <v-app-bar class="grey lighten-5" height="74" app>
      <img class="mx-2" src="images/fanta.svg" style="height:150px; margin-top:100px" />
      <span class="text-truncate text-h4 blue-grey--text darken-1" style="font-family: Poppins">Fancy Fanta</span>
    </v-app-bar>
    <v-main>
      <div>
        <v-navigation-drawer v-model="drawer" :mini-variant.sync="mini" permanent absolute style="margin-top: 150px; margin-left: 20px; height: 299px; border: 1px solid grey">
          <v-list-item class="px-2">
            <v-list-item-avatar>
              <v-img
                src="https://lh3.googleusercontent.com/fife/AAWUweWEGpWzxrKHivZtKRlkRSb7fKTUCj9oJUdS72UnNk7w4qDcfzfUmQTIR3nipdon_3mFcJdJZkYyOOJfwe4FRhNOz-YQcY8_ev0WsbcIfuUVFtA5OClXuaVzbZSorFtgH3mCvVY6jgxcCMEBRk3Y-bGK6tptwhr8QQlpRvPSFubteXzSJ1k7inXabNjGA1_9m0PFvV3DLAqK6Bt9RfspoZtvhGdIy9wvJp9USZvavNxj191v4VRsqZ27k2xRNt_OU_xIWOjsCGSxGy8OuzrW60A-9pJ3y5-kBQxB4B08or-W0yB53DvJRy-RZrldSbGH_bQ6ZmSPK54nvHNi0N-XcD3B3gRU-GTIL3-EbjmPA1Uy9yPJUyXWr2mOlvIesM2uL2pIlMfMdl02v-ZtIyt-NRxTQJRMhJkMbSS-9tz7OA37zWyq5tqfzOXaqknbwDUqiDBhii__CZqT_CZ7XbU2WaYDRQZNqBNgTn0vIoBIswW1ZAgj740y3lehQt9PetdPDuEqwcMdL_sLAadmDqI5b-zVJzn_jWZXh1kfNBIrNvRo0FNBBYzuS6b7AkWdz6aKAMH14K3TP0fL3RAYl92epJ9XTz6FmLih65nmY0SprIW0Z4zmNM7HXc1E_GjTzD3KibWc9ghsvKW4RecYrk0y4okCrXO996ZM7sw1FHYjErqpW1MRf8hqCxx7eJOflKNOcF34FCSnk153Fzdcm4avndhxkHyCcAOjpIBiUvJUkd1cHtA=s128"
              ></v-img>
            </v-list-item-avatar>

            <v-list-item-title>His Student</v-list-item-title>

            <v-btn class="grey" icon @click.stop="mini = !mini">
              <v-icon>mdi-chevron-left</v-icon>
            </v-btn>
          </v-list-item>

          <v-divider></v-divider>

          <v-list>
            <v-list-item v-for="route in routes" :key="route.name" :to="route.link" link active-class="orange">
              <v-list-item-icon>
                <v-icon>{{ route.icon }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>{{ route.name }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-navigation-drawer>
      </div>
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
    drawer: true,
    routes: [
      { name: 'Home', link: '/', icon: 'mdi-home-city' },
      { name: 'Products', link: 'products', icon: 'mdi-cash' },
      { name: 'Team', link: 'team', icon: 'mdi-account-group' },
      { name: 'About', link: 'about', icon: 'mdi-information' },
    ],
    mini: true,
  }),
};
</script>
