<template>
  <v-app>
    <v-app-bar
      app
      color="white"
      elevation="0"
    >
      <div class="d-flex align-center" >
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>
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
    <!-- <v-toolbar>
      <v-toolbar-side-icon></v-toolbar-side-icon>
      <v-toolbar-title>Title</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat>Link One</v-btn>
        <v-btn flat>Link Two</v-btn>
        <v-btn flat>Link Three</v-btn>
        <v-list>
          <v-list-tile>
            <v-list-tile-action>
              <v-icon>mdi-home</v-icon>
            </v-list-tile-action>
            <v-list-tile-title>Home</v-list-tile-title>
          </v-list-tile>
        </v-list>
        <v-list>
          <v-list-group
            prepend-icon="mdi-account-circle"
            value="true"
          >
            <v-list-tile slot="activator">
              <v-list-tile-title>Users</v-list-tile-title>
            </v-list-tile>
  
            <v-list-group
              no-action
              sub-group
              value="true"
            >
              <v-list-tile slot="activator">
                <v-list-tile-title>Admin</v-list-tile-title>
              </v-list-tile>

               <v-list-tile
                v-for="(admin, i) in admins"
                :key="i"
                
              >
                <v-list-tile-title v-text="admin[0]"></v-list-tile-title>
                <v-list-tile-action>
                  <v-icon v-text="admin[1]"></v-icon>
                </v-list-tile-action>
              </v-list-tile> 
            </v-list-group>
          </v-list-group>
        </v-list>
        <v-list>
          <v-list-group
            sub-group
            no-action
          >
            <v-list-tile slot="activator">
              <v-list-tile-title>Actions</v-list-tile-title>
            </v-list-tile>

          
          </v-list-group>
        </v-list>
      </v-toolbar-items>
    </v-toolbar> -->
    
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
