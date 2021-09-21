<template>
  <v-app>
    <v-app-bar class="grey lighten-5" height="74" app>
      <img class="mx-2" src="images/fanta.svg" style="height:150px; margin-top:100px" />
      <span class="text-truncate text-h4 blue-grey--text darken-1" style="font-family: Poppins">Fancy Fanta</span>
    </v-app-bar>
    <v-main>
      <v-navigation-drawer v-model="drawer" :mini-variant.sync="mini" permanent absolute>
        <v-list-item class="px-2">
          <v-list-item-avatar>
            <v-img
              src="https://lh3.googleusercontent.com/fife/AAWUweX2NcfcMet5KvXIuUqgbdbrvhY-vvq4GQ5EMTtCFioQ_GAFLzR84HCGawetWs7J81wHA9Ifh3nsSlnPezjbiLs0UblvF-1IsX7RhcxdjX5woyJ4V7zicSL2i6Smiwx7Ce7Ob2eMm-I1Yvlq8NT6Xoo0WwKa_iHvXB7akDWztc4CtTzmjOEI3R2Gz-IKxWvE_PeHZqNy-dYrDREbFk_uFQPN9Ws1AyCS1ixMTl0gBbOPA7RJyq6MWwqb27LHh1GeGG4LLUaiRJOr_qeS0SXuSaMIf5APZUu35Z0pYWbDE2fkUAtNJqh8Vc985rEk-A3X5kxxjqAPH6zuzUWzNs5LgZHm1LIrMgE4pYbwsFxk2wkmnPIk2kS-HSbVAwkmr9Re1kN_aUzF2TlE6A9WHWAbj48V9AO52d-saeoz8IZIH0Du6HbxSgNZkZp5qinrS3GOn6gKrX3JCQ8y1lXljfaKS41UcQRXmTaqIp8l4ItjYmUWMZKTPn24ny8iYB4sVYQipsrNgTkv2ipjgaB4T8fzpYP4vOnD0unf9ks5c5oaWKzCLS-z-FIgs-SRgbkaeqa3kDtM4JO8U5NJDEtY63lsDHuefBfLtwg-o4P96mQQeD7mQK2R5mDTYVDwl2cQFane1hX9-M9ldp4czEm7bXsVQdpzhiRUGnelwlD1Y73VS4o1MSDVKUfgGhXM6BScnD8AXJ6xfNxVEQhKimMyk4SZ3WnNkmA9DlO_2JATMJ1QkOh5Wg=s64-c"
            ></v-img>
          </v-list-item-avatar>

          <v-list-item-title>His Student</v-list-item-title>

          <v-btn icon @click.stop="mini = !mini">
            <v-icon>mdi-chevron-left</v-icon>
          </v-btn>
        </v-list-item>

        <v-divider></v-divider>

        <v-list>
          <v-list-item v-for="route in routes" :key="route.name" link>
            <v-list-item-icon>
              <v-icon>{{ route.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ route.name }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
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
