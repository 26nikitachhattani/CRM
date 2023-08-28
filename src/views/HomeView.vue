<template>
  <div>
    <!-- <hello-world /> -->

    <v-container fluid>
      <div class="heading-text mx-14">Forumx Resources</div>
      <div class="sub-text my-1 mx-14">
        Learn how to make the most of your Forumx Forum experience.
      </div>
    
      <v-row class="py-7 mx-14">
        <v-col cols="9" class="mx-0 pa-0">
          <list />
        </v-col>
        <v-col class="mx-1 pa-0">
          <discussion />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
// import HelloWorld from "../components/HelloWorld";
import list from "../components/list";
import discussion from "../components/sideCard";
export default {
  name: "HomeView",
  components: {
    // HelloWorld,
    list,
    discussion,
  },
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&display=swap");
.heading-text {
  font: normal normal 600 20px/27px Open Sans;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
}
.sub-text {
  font: normal normal normal 16px/22px Open Sans;
  letter-spacing: 0px;
  color: #304655;
  opacity: 1;
}

</style>