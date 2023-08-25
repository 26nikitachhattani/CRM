<template>
  <div style="background-color: #F5F5F5;">
    <v-container fluid >
      <v-row class="py-7 mx-14 justify-space-around">
        <v-col cols="9">
           <CreateForm/>
        </v-col>
       
    </v-row>
    </v-container>
    
  </div>
</template>

<script>
import CreateForm from "../components/createForm";
// import list from "../components/list";
// import discussion from "../components/sideCard";
export default {
  name: "HomeView",
  components: {
    CreateForm
    // list,
    // discussion
  },
};
</script>
