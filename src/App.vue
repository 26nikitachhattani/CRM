<template>
  <div>
    <v-app>
      <v-app-bar app color="white" elevation="0">
        <div class="d-flex align-center">
          <v-img
            alt="Logo"
            class="mr-10"
            contain
            height="70px"
            src="@/assets/logo.svg"
            transition="scale-transition"
            width="100"
          />
        </div>
        <v-btn elevation="0" class="transparent btn-css" @click="goToHome"
          >All Topics</v-btn
        >
        <v-btn elevation="0" class="transparent btn-css">Help</v-btn>
        <v-spacer></v-spacer>
        <v-text-field
          class="my-2"
          label="Search"
          prepend-inner-icon="mdi-magnify"
          hide-details
          outlined
          dense
        ></v-text-field>
        <v-spacer></v-spacer>
        <v-btn
          href="https://github.com/vuetifyjs/vuetify/releases/latest"
          target="_blank"
          text
        >
          <!-- <span class="mr-2">Latest Release</span> -->
          <v-avatar class="mx-2" size="40px">
            <img
              alt="Avatar"
              src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
            />
          </v-avatar>
          <v-icon>mdi-open-in-new</v-icon>
        </v-btn>
      </v-app-bar>
      <v-main style="background-color: #f5f5f5">
        <router-view />
      </v-main>
    </v-app>
  </div>
</template>
<script>
export default {
  name: "App",
  data: () => ({
    dialog: false,
  }),
  methods: {
    loggedIn() {
      if (localStorage.getItem("user") === null) {
        this.dialog = true;
      }
    },
    goToHome() {
      this.$router.push("/");
    },
  },
  created() {
    // this.loggedIn()
  },
};
</script>
