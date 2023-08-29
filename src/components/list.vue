<template>
  <div>
    <v-container>
      <div class="my-2 d-md-flex">
        <div class="d-flex">
          <v-btn
            style="border: 1px solid #e5e5e5"
            elevation="0"
            class="white btn-class pa-4 text-center rounded-r-0 rounded-l-xl"
          >
            Activity
          </v-btn>
          <v-btn
            style="border: 1px solid #e5e5e5"
            elevation="0"
            class="white btn-class pa-4 text-center rounded-l-0 rounded-r-xl"
          >
            Status
          </v-btn>
        </div>
        <v-spacer></v-spacer>
        <v-btn icon-and-text elevation="0" class="dis-btn primary" to="/create"
          ><v-icon>mdi-plus</v-icon>Start a Discussion</v-btn
        >
      </div>
      <v-row justify="center" class="ma-sm-1 justify-space-between">
        <v-col cols="12">
          <div v-for="(message, i) in messages" :key="i" class="card-div" @click="goToTopicPage(i)">
            <v-card
              class="my-2 card-box"
              elevation="0"
              style="border: 0.5px solid #f7b971"
            >
              <v-card-text>
                <v-row align="center" class="spacer" no-gutters>
                  <v-col class="" sm="12" md="5">
                    <div>
                      <strong v-html="message.title"></strong>
                      <div v-html="message.description" />
                    </div>
                  </v-col>
                  <v-col cols="1" class=""></v-col>
                  <v-col class="" cols="12" sm="12" md="3">
                    <div class="text-center d-flex">
                      <div>
                        <div class="replies-count-text">0 replies</div>
                        <div class="views-text">0 Views</div>
                      </div>
                      <v-avatar class="mx-2" size="40px">
                        <img
                          alt="Avatar"
                          src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                        />
                      </v-avatar>
                      <div>
                        <div class="replies-count-text"></div>
                        <div class="views-text">
                          {{ message.date }}
                        </div>
                      </div>
                    </div>
                  </v-col>

                  <v-col
                    sm="12"
                    md="2"
                    v-if="message.description"
                    class="grey--text text-right text-truncate hidden-sm-and-down"
                  >
                    <div class="text-right">
                      <v-icon class="mx-2">mdi-star</v-icon>
                      <v-icon class="mx-2">mdi-checkbox-marked-circle</v-icon>
                    </div>
                  </v-col>
                </v-row>
              </v-card-text>
            </v-card>
          </div>
        </v-col>
      </v-row>
      <!-- <v-pagination v-model="page" class="my-4" left :length="4"></v-pagination> -->
    </v-container>
  </div>
</template>
 
<script>
export default {
  name: "cardList",
  data: () => ({ 
    page: 1,
    messages: [],
  }),
  methods: {
    goToTopicPage(index){
      this.$router.push(`/topic/${index}`)
    }
  },
  created() {
    this.messages = JSON.parse(localStorage.getItem("topics"));
  },
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
.v-card--link:hover {
  background: blue;
}

.v-card--link:hover::before {
  opacity: 0;
}
.card-div:hover > .card-box{
  background: #49A97233;
}
</style>