<template>
  <div>
    <div class="mb-3 title-text">New Post</div>
    <v-sheet color="my-3 py-5 px-3 info-sheet">
      Your content will need to be approved by a moderator
    </v-sheet>
    <div>
      <v-alert
        v-model="alert"
        dismissible
        color="white"
        elevation="0 "
        icon="mdi-twitter"
      >
        Forums Forum is a peer-to-peer community for anyone building their
        website and online business.
      </v-alert>

      <div class="text-center">
        <v-btn v-if="!alert" dark @click="alert = true"> Reset Alert </v-btn>
      </div>
    </div>
    <v-card height="700">
      <v-card-text class="my-3">
        <div class="my-2 sub-header">Title <span>Required</span></div>
        <v-text-field
          v-model="title"
          label="title"
          prepend-inner-icon="mdi-plus"
          class="mt-1"
          outlined
        ></v-text-field>
        <div class="my-2 sub-header">Tags <span>Required</span></div>
        <v-text-field
          v-model="tag"
          label="Tag"
          prepend-inner-icon="mdi-plus"
          class="mt-1"
          outlined
        ></v-text-field>
        <div class="my-1 sub-header">Discussion <span>Required</span></div>
        <quillEditor hide-details v-model="description" id="editor-container"  />
      </v-card-text>
      <v-card-actions class="my-10">
        <v-btn outlined rounded text @click="submit"> Button </v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
//import QuillEditor from "./common/QuillEditor.vue";
import { quillEditor } from "vue-quill-editor";
import "quill/dist/quill.snow.css";
//import { quillEditor } from "vue-quill-editor";
export default {
  data() {
    return {
      alert: true,
      title: "",
      tag: "",
      description: "",
      topics: [],
    };
  },
  watch: {
  },
  methods: {
    submit() {
      if (localStorage.getItem("topics") !== null) {
        this.topics = JSON.parse(localStorage.getItem("topics"));
      } else {
        this.topics = []; // Initialize topics as an empty array if it doesn't exist in localStorage
      }

      this.topics.push({
        title: this.title,
        tag: this.tag,
        description: this.description,
      });

      // Save the updated topics array back to localStorage
      localStorage.setItem("topics", JSON.stringify(this.topics));
    },
  },
  components: {
    quillEditor,
    //quillEditor,
  },
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&display=swap");
.info-sheet {
  background: #e5e5e5 0% 0% no-repeat padding-box;
  border: 1px solid #dddddd;
  border-radius: 5px;
  opacity: 1;
  color: #b72828;
  font: normal normal bold 17px/23px Open Sans;
  letter-spacing: 0px;
}
.title-text {
  font: normal normal 600 24px Open Sans;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
}
.sub-header {
  text-align: left;
  font: normal normal 600 13px Open Sans;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
}
.sub-header > span {
  text-align: left;
  font: normal normal 600 10px/14px Open Sans;
  letter-spacing: 0px;
  color: #b72828;
  text-transform: uppercase;
  opacity: 1;
}
</style>
