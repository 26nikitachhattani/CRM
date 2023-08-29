<template>
  <v-app>
    <v-app-bar
      app
      color="white"
      elevation="0"
    >
      <div class="d-flex align-center" >
        <v-img
          alt="Logo"
          class="mr-10 "
          contain
          height="70px"
          src="@/assets/logo.svg"
          transition="scale-transition"
          width="100"
        />
      </div>
      <v-btn elevation="0" class="transparent btn-css" @click="this.$router.push('/')" >All Topics</v-btn>
      <v-btn elevation="0" class="transparent btn-css" >Help</v-btn>
      <v-spacer></v-spacer>
      <v-text-field class="my-2" label="Search" prepend-inner-icon="mdi-magnify" hide-details outlined dense></v-text-field>
      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>
      <v-main style="background-color: #F5F5F5;">
      <router-view/>
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
