\<template>
  <div>
    <v-container>
      <v-sheet elevation="0" class="py-4 px-8">
        <div>
          <h3 class="title">
            Fuel user engagement with seriously powerful in-app chats
          </h3>
        </div>
        <v-divider class="my-2"></v-divider>
        <div class="d-flex my-2" style="align-items: center">
          <v-avatar class="mx-2" size="40px">
            <img
              alt="Avatar"
              src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
            />
          </v-avatar>
          <div class="mx-2">April 3, 2022</div>
          <div>0 replies</div>
          <v-spacer></v-spacer>
        </div>
        <v-divider></v-divider>
        <div class="my-2 d-flex" style="align-items: center">
          <div class="mx-2 topic-response-text">
            Replies<span class="mx-0">10</span>
          </div>
          <div class="mx-2 topic-response-text">
            Created <span>1 Year</span>
          </div>
          <div class="mx-2 topic-response-text">2 days</div>
          <v-spacer></v-spacer>
          <v-btn class="primary btn-css" elevation="0"
            >Reply To This Topic</v-btn
          >
        </div>
        <v-card
          class="my-2 card-box"
          v-for="(message, i) in messages"
          :key="i"
          elevation="0"
          style="border: 1px solid #dddddd"
        >
          <v-card-text>
            <v-row align="center" class="spacer" no-gutters>
              <v-col class="" sm="12" md="12">
                <div>
                  <strong v-html="message.title"></strong>
                  <div>{{ message.excerpt }}</div>
                </div>
                <v-divider class="my-1"></v-divider>
                <div class="d-flex" style="align-items: center">
                  <v-chip
                    class="ma-1 pa-3"
                    color="#dddddd"
                    text-color="black"
                    outlined
                  >
                    <v-icon left> mdi-thumb-up </v-icon>
                    2
                  </v-chip>
                  <v-chip
                    class="ma-1 pa-3"
                    color="#dddddd"
                    text-color="black"
                    outlined
                  >
                    <v-icon left> mdi-heart </v-icon>
                    2
                  </v-chip>
                  <v-spacer></v-spacer>
                  <v-avatar class="mx-2" size="40px">
                    <img
                      alt="Avatar"
                      src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                    />
                  </v-avatar>
                  <div class="mx-1">James bond</div>
                  <div>April 3, 2022</div>
                </div>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-sheet>
    </v-container>
  </div>
</template>
 
<script>
export default {
  name: "cardList",
  data: () => ({
    page: 1,
    messages: [
      {
        avatar: "https://avatars0.githubusercontent.com/u/9064066?v=4&s=460",
        name: "James S. Booth",
        total: 3,
        view: "10.3k views",
        title: "Fuel user engagement with seriously powerful in-app chats",
        excerpt:
          "Our in-app Chat SDK can help you develop the communication features your users need to connect and interact with each other anytime, anywhere.",
      },
      {
        avatar: "https://avatars0.githubusercontent.com/u/9064066?v=4&s=460",
        name: "Social",
        new: 1,
        total: 3,
        view: "10.3k views",
        title: "Twitter",
        excerpt:
          "Hello, Does anyone have a work around for locking the page titles in the navigation bar when viewing the website on a mobile device?",
      },
      {
        avatar: "https://avatars0.githubusercontent.com/u/9064066?v=4&s=460",
        name: "Promos",
        new: 2,
        total: 4,
        view: "10.3k views",
        title: "Shop your way",
        excerpt:
          "Hello, Does anyone have a work around for locking the page titles in the navigation bar when viewing the website on a mobile device?",
      },
      {
        avatar: "https://avatars0.githubusercontent.com/u/9064066?v=4&s=460",
        name: "John Leider",
        total: 3,
        view: "10.3k views",
        title: "Fuel user engagement with seriously powerful in-app chats",
        excerpt:
          "Our in-app Chat SDK can help you develop the communication features your users need to connect and interact with each other anytime, anywhere.",
      },
      {
        color: "red",
        icon: "mdi-account-multiple",
        name: "Social",
        new: 1,
        total: 3,
        title: "Twitter",
        view: "10.3k views",
        excerpt:
          "Our in-app Chat SDK can help you develop the communication features your users need to connect and interact with each other anytime, anywhere.",
      },
    ],
  }),
  methods: {},
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&display=swap");
.replies-count-text {
  text-align: left;
  font: normal normal medium 13px/18px Open Sans;
  letter-spacing: 0px;
  color: #304655;
  opacity: 1;
}
.views-text {
  font: normal normal medium 13px/18px Open Sans;
  letter-spacing: 0px;
  color: #82888d;
  opacity: 1;
}
.btn-class {
  border: 0.5px solid #f5f5f5;
}
.dis-btn {
  font: normal normal 600 15px/20px Open Sans;
  letter-spacing: 0px;
  color: #ffffff;
  text-transform: capitalize;
  opacity: 1;
}
.v-col >>> .card-box :hover {
  background: #49a97233 0% 0% no-repeat padding-box;
}
.topic-response-text {
  font: normal normal normal 17px/23px Open Sans;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
}
.topic-response-text >>> span {
  font: normal normal 600 20px/27px Open Sans;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
}
.title {
  font: normal normal 600 30px/41px Open Sans;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
}
</style>