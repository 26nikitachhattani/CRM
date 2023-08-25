<template>
  <div >
    <!-- <hello-world /> -->
    <v-container fluid >
      <v-row class="py-7 mx-14">
      <v-col cols="9" class="mx-0 pa-0">
        <list />
      </v-col>
      <v-col class="mx-1 pa-0">
        <discussion/>
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
    discussion
  },
};
</script>
