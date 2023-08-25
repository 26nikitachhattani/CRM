<template>
 <div>
  <v-container >
    <v-row justify="center">
        <v-col cols="12">
        <v-card
          v-for="(message, i) in messages"
          :key="i"
          hide-actions
          class="my-2"
          elevation="0"
          style="border: 0.5px solid #F7B971"
        >
          <v-card-text>

            <v-row
              align="center"
              class="spacer"
              no-gutters
            >
              <!-- <v-col
                cols="4"
                sm="2"
                md="1"
              >
                <v-avatar
                  size="36px"
                >
                  <img
                    v-if="message.avatar"
                    alt="Avatar"
                    src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                  >
                  <v-icon
                    v-else
                    :color="message.color"
                    
                  >{{message.icon}}</v-icon>
                </v-avatar>
              </v-col> -->

              <v-col
                class="hidden-xs-only"
                sm="5"
                md="5"
              >
                <strong v-html="message.name"></strong>
                <span
                  v-if="message.total"
                  class="grey--text"
                >
                  &nbsp;({{ message.total }})
                </span>
                  <div>
                    <strong v-html="message.title"></strong>
                  </div>
              </v-col>

              <v-col
                class="text-no-wrap"
                cols="5"
                sm="3"
              >
                <v-chip
                  v-if="message.new"
                  :color="`${message.color} lighten-4`"
                  class="ml-0 mr-2 black--text"
                  label
                  small
                >
                  {{ message.new }} new
                </v-chip>
                <strong v-html="message.title"></strong>
              </v-col>

              <v-col
                v-if="message.excerpt"
                class="grey--text text-truncate hidden-sm-and-down"
              >
                &mdash;
                {{ message.excerpt }}
              </v-col>
            </v-row>
          </v-card-text>
         
        </v-card>
        </v-col>
    </v-row>
  </v-container>
 </div>
</template>
 
<script>
  export default {
    name: 'cardList',
    data: () => ({
      messages: [
        {
          avatar: 'https://avatars0.githubusercontent.com/u/9064066?v=4&s=460',
          name: 'John Leider',
          title: 'Welcome to Vuetify!',
          excerpt: 'Thank you for joining our community...',
        },
        {
          color: 'red',
          icon: 'mdi-account-multiple',
          name: 'Social',
          new: 1,
          total: 3,
          title: 'Twitter',
        },
        {
          color: 'teal',
          icon: 'mdi-tag',
          name: 'Promos',
          new: 2,
          total: 4,
          title: 'Shop your way',
          exceprt: 'New deals available, Join Today',
        },
         {
          avatar: 'https://avatars0.githubusercontent.com/u/9064066?v=4&s=460',
          name: 'John Leider',
          title: 'Welcome to Vuetify!',
          excerpt: 'Thank you for joining our community...',
        },
        {
          color: 'red',
          icon: 'mdi-account-multiple',
          name: 'Social',
          new: 1,
          total: 3,
          title: 'Twitter',
        },
      ],
      lorem: 'Lorem ipsum dolor sit amet, at aliquam vivendum vel, everti delicatissimi cu eos. Dico iuvaret debitis mel an, et cum zril menandri. Eum in consul legimus accusam. Ea dico abhorreant duo, quo illum minimum incorrupte no, nostro voluptaria sea eu. Suas eligendi ius at, at nemore equidem est. Sed in error hendrerit, in consul constituam cum.',
    }),
  }
</script>