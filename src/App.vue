<template>
  <v-app>
    <v-main>
      <v-row class="py-0 my-0">
        <v-col sm="4" md="4" lg="4" xl="4" class="ml-5 py-0 my-0">
          <v-img dark width="150" height="50" class="mb-0 mt-3" src="../src/assets/logo.jpg" />
        </v-col>
        <v-col
          sm="5"
          md="5"
          lg="5"
          xl="5"
          class="ml-auto d-flex justify-space-around align-center mt-2"
        >
          <router-link class="nav" to="/">HOME</router-link>
          <router-link class="nav" to="/portfolio">PORTFOLIO</router-link>
          <router-link class="nav" to="/about">ABOUT</router-link>
          <router-link class="nav" to="/contact">CONTACT</router-link>
          <span class="mx-0">
            <v-icon
              @click="openTab(icon.to)"
              class="mx-2"
              large
              :color="icon.color"
              v-for="icon in icons"
              :key="icon.i"
              >{{ icon.icon }}</v-icon
            >
          </span>
        </v-col>
      </v-row>
      <v-container fluid class="py-0 px-0 my-0">
        <router-view></router-view>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    icons: [
      {
        icon: "mdi-facebook",
        color: "#29487D",
        to: "https://www.facebook.com/NorthAlpinePhoto",
      },
      {
        icon: "mdi-instagram",
        color: "#F58529",
        to: "https://www.instagram.com/north_alpine_photo/",
      },
      {
        icon: "mdi-linkedin",
        color: "#0077B5",
        to: "https://www.linkedin.com/in/kurt-yates-958563a8/",
      },
    ],
  }),
  methods: {
    openTab(url) {
      window.open(`${url}`);
    },
  },
};
</script>

<style scoped>
.nav {
  color: black;
  text-decoration: none;
  list-style: none;
}
</style>
