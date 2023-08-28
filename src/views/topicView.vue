<template>
  <div style="background-color: #f5f5f5">
    <v-container fluid>
      <v-row class="py-7 mx-14 justify-space-around">
        <v-col cols="9">
          <Chats />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
import Chats from "../components/chatBox/chats";
export default {
  name: "RepliesView",
  components: {
    Chats,
  },
};
</script>
