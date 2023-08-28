<template>
  <div>
    <v-card
      class=""
      style="
        background: linear-gradient(270deg, #5f88f7 0%, #2991ea 100%) 
      "
      dark
      max-width="400"
    >
      <v-card-text class="heading-text">
        Circle Day: Build <br/> Your Toolkit
      </v-card-text>

      <v-card-actions>
        <v-list-item class="grow">
          <v-list-item-avatar color="grey darken-3">
            <v-img
              class="elevation-6"
              alt=""
              src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
            ></v-img>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title>Evan You</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-card-actions>
    </v-card>
    <div>Popular Contributors</div>
    <v-row class="text-center my-0">
      <v-col cols="4" class="" v-for="i in items" :key="i">
        <div>
          <v-avatar color="" size="55">
            <v-img class="elevation-6" alt="" :src="i.avatar"></v-img>
          </v-avatar>
          <div class="name-text">jamessbooth</div>
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
          name: "jamessbooth",
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
.heading-text{
  
}
</style>