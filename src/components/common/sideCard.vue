<template>
  <div>
    <v-card
      class="my-5"
      style="background: linear-gradient(270deg, #5f88f7 0%, #2991ea 100%)"
      dark
      elevation="0"
      max-width="400"
    >
      <v-card-text class="heading-text">
        Circle Day: Build <br />
        Your Toolkit
      </v-card-text>

      <v-card-actions>
        <v-list-item class="grow"> 
          <v-list-item-content>
            <v-list-item-title>50 days away</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-card-actions>
    </v-card>
    <div class="my-3 text-heading">Popular Contributors</div>
    <v-row class="text-center my-0">
      <v-col cols="4" class="justify-center" v-for="i in items" :key="i">
        <div class="text-center">
          <v-avatar color="" size="55">
            <v-img class="elevation-6" alt="" :src="i.avatar"></v-img>
          </v-avatar>
          <div class="name-text" style="text-align: center">james</div>
        </div>
      </v-col>
    </v-row>
  </div>
</template>
<script>
export default {
  data() {
    return {
      items: [
        {
          avatar: "https://cdn.vuetifyjs.com/images/lists/1.jpg",
          title: "Brunch this weekend?",
          name: "james booth",
          subtitle: `<span class="text--primary">Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?`,
        },

        {
          avatar: "https://cdn.vuetifyjs.com/images/lists/2.jpg",
          title: 'Summer BBQ <span class="grey--text text--lighten-1">4</span>',
          subtitle: `<span class="text--primary">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.`,
        },

        {
          avatar: "https://cdn.vuetifyjs.com/images/lists/3.jpg",
          title: "Oui oui",
          subtitle:
            '<span class="text--primary">Sandra Adams</span> &mdash; Do you have Paris recommendations? Have you ever been?',
        },

        {
          avatar: "https://cdn.vuetifyjs.com/images/lists/4.jpg",
          title: "Birthday gift",
          subtitle:
            '<span class="text--primary">Trevor Hansen</span> &mdash; Have any ideas about what we should get Heidi for her birthday?',
        },

        {
          avatar: "https://cdn.vuetifyjs.com/images/lists/5.jpg",
          title: "Recipe to try",
          subtitle:
            '<span class="text--primary">Britta Holt</span> &mdash; We should eat this: Grate, Squash, Corn, and tomatillo Tacos.',
        },
        {
          avatar: "https://cdn.vuetifyjs.com/images/lists/1.jpg",
          title: "Brunch this weekend?",
          subtitle: `<span class="text--primary">Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?`,
        },
      ],
    };
  },
};
</script>
<style scoped>
.card-text {
  font: normal normal bold 28px/47px Open Sans;
  letter-spacing: 0px;
  color: #ffffff;
  opacity: 1;
}
.name-text {
  text-align: left;
  font: normal normal 600 13px/18px Open Sans;
  letter-spacing: 0px;
  color: #304655;
  opacity: 1;
}
.heading-text {
  font: normal normal bold 28px/47px Open Sans;
  letter-spacing: 0px;
  color: #ffffff;
  opacity: 1;
}
.text-heading {
  font: normal normal 600 20px/27px Open Sans;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
}
</style>